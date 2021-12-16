---
title: "What is SQL now?"
date: 2021-12-16T12:56:38+03:00
draft: false
---

What is SQL now?

SQL is Esperanto in the data world. But unlike "Lingwe Uniwersala" SQL was reached world popularity and wide spreading.

Initialy SQL was invented in 70's special for databases. Even then it creators was aimed to create a simple and powerfull data language for wide range of users, with not only IT background, such as engineers, scientists, researchers, analytics, managers etc. SQL first of all was made by humans for humans, not for machines.

Currently SQL are applied not only in relational databases, but also in NoSQL DB, streaming platforms, In-Memory grids etc. SQL is one of the oldest computer language widely spread over the World in nowaday.

What's the secret of SQL success, health and long life? General SQL advanatage is a declarativeness and high-level. We don't explain how we want to receive the data, we describe only what we want to receive. If you want to get employee with names starting with the letter "A", then just politely ask your system about it:

```sql
select name
  from employee
 where name like 'A%'
```

SQL can be used interactively (and it's good), but this one can also be hiden from users and engineers under the hood in various programs, tools and services. And there is a problem - you, as a data owner, loose control, clarity and safety of the data. In futher posts we will be able discuss "database as Code" ideas and how can they help us.
