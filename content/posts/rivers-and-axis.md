---
title: "Rivers and Axis"
date: 2022-01-31T22:56:38+03:00
draft: false
tags: ['SQL']
---

It's hard to find at least two people who would format the same SQL query in the same way. Everyone has their own style and their own arguments.

And everyone is absolutely sure that this is a single right way.

At the same time, SQL is quite unusual language and provides many formatting options.

But almost all of these methods have one unpleasant detail. In typography, it is called a [river](https://en.wikipedia.org/wiki/River_(typography))

But legendary Joe Celko in his book ["Joe Celko's SQL Programming Style"](https://www.amazon.com/Celkos-Programming-Kaufmann-Management-Systems/dp/0120887975) sad: "No River. Keep to Axis."

![Axis](/axis-advance.png)

```sql
select *
  from persons p
  join departments d on 
 where p.salary > 
       (select avg(salary) as salary_avg
          from persons
          join departments d on 
         where age > 35)
```

At the first glance, we already see three separate entities. It is not difficult to find the main axis with main query.

 

It doesn't matter who formats how - subqueries placement, using indents. Main - just keep to axis.

Maybe you find other methods too keep your axis.


<!-- My new blog post about Rivers and Axis in SQL --> 
