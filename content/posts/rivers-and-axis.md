---
title: "Rivers and Axis"
date: 2022-01-31T22:56:38+03:00
draft: false
tags: ['SQL']
---

It's hard to find at least two people who would format the same SQL query in the same way. Everyone has their own style and their own arguments. And everyone is absolutely sure that this is the only right way.

That was to be expected, because of the declarative nature of SQL. In imperative program languages, we define and control the order of statements execution, and it affects how we format our code. But in SQL query we don't know at all the order of execution in advance and it deprives us of an important reference point. As a result, we have a lot of formatting options.

But almost all of these options have one common unpleasant detail. In typography, it is called a [river](https://en.wikipedia.org/wiki/River_(typography)) and it is considered to be bad typography. Let's look at a simple query. The river (marked red) tore our query into two jagged parts and makes the code more difficult to read.

![Axis](/rivers-and-axis/river-simple-marked-small.png)
<!--
```sql
select e.first_name,
       e.last_name,
       e.salary,
       d.name,
       j.name
from employee e
join departments d on d.id = e.dept_id
join jobs j on j.id = e.job_id
where d.name = 'IT'
  and j.name = 'Engineer'
  and e.salary > 100
```
-->

But legendary Joe Celko in his book ["Joe Celko's SQL Programming Style"](https://www.amazon.com/Celkos-Programming-Kaufmann-Management-Systems/dp/0120887975) sad: let's turn our rivers into axes. Same query but with the axis instead the river:

![Axis](/rivers-and-axis/axis-simple-marked-small.png)

<!--
```sql
select e.first_name
     , e.last_name
     , e.salary
     , d.name as department_name
     , j.name as job_name
  from employee e
  join departments d on d.id = e.dept_id
  join jobs j on j.id = e.job_id
 where d.name = 'IT'
   and j.name = 'Engineer'
   and e.salary > 100
```
-->

Let's look at a more complicated query with subqueries:

![Axis](/rivers-and-axis/axis-advance-marked.png)

<!--
```sql
select e.first_name
     , e.last_name
     , e.salary
     , d.name
     , j.name
     , (select sum(o.cost)
          from orders o
         where o.employee_id = e.id
           and o.status = 'closed')
  from employee e
  join departments d on d.id = e.dept_id
  join jobs j on j.id = e.job_id
 where e.salary > (select avg(se.salary)
                     from employee se
                     join departments sd on sd.id = se.dept_id
                    where d.name = 'IT')
```
-->

We immediately visually detect three axes and three corresponding queries. This allows us to quickly and easily find out what this query does.

In this post I use my way to build an axis (maybe not the best), surely you can find other methods for this.
