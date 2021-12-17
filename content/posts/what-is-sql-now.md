---
title: "What is SQL now?"
date: 2021-12-16T12:56:38+03:00
draft: false
---

SQL is Esperanto in the data world. But unlike "Lingwe Uniwersala" SQL became world-known and really common.

Initially SQL was invented in 70 special for databases. Even then its creators aimed to create a simple and powerful data language for a wide range of users, with not only IT background, such as engineers, scientists, researchers, analytics, managers etc. SQL first of all was made by humans for humans, not for machines.

Currently SQL is applied not only in relational databases, but also in NoSQL DB, streaming platforms, In-Memory grids etc. SQL is one of the oldest computer languages widely spread over the World nowadays.

What's the secret of SQL success, health and long life? General SQL advantage is that it is declarative and high-level. We don't explain how we want to receive the data, we describe only what we want to receive. If you want to get employee with names starting with the letter "A", then just politely ask your system for it:

```sql
select name
  from employee
 where name like 'A%'
```

SQL can be used interactively (and it's good), but this one can also be hidden from users and engineers under the hood in various programs, tools and services. And there is a problem - you, as a data owner, lose control, clarity and safety of the data. In further posts we will be able to discuss "database as Code" ideas and how they can help us.
