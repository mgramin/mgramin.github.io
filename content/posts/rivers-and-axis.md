---
title: "Rivers and Axis"
date: 2021-12-17T22:56:38+03:00
draft: false
tags: ['SQL']
---

```sql
select *
  from persons p
  join departments d on 
 where p.salary > (select avg(salary)
                     from persons
                     join departments d on 
                    where age > 35)
```

-- Не важно кто как форматирует, переносит подзапросы, использует отступы, гланое придерживаться "осей"
