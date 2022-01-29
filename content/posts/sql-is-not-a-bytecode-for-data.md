---
title: "SQL is not a bytecode for Data"
date: 2022-01-25T12:56:38+03:00
draft: false
tags: ['SQL', 'database-as-code']
---

For many people, SQL is still a “low-level” computer language for data. It is considered an ancient and difficult to understand language, designed for special secret engineers with special secret skills. In this way, a mere mortal should not write SQL queries and should rely on special tools. And we are used to the fact that almost all ORM, DB managers, monitoring tools, and other DB tools generate tons of "tricky" queries against our data, turning SQL into dumb bytecode. And we can basically just observe this process and hope for the best.

But SQL first of all was invented [especially for humans](/posts/what-is-sql-now), not for machines. So let's treat SQL like a normal computer language (such as Java, C#, C++, etc) and try to follow some generally accepted principles:

- SQL queries are *first-class citizens* in your system.

- *Git* (or any other VCS) is the single source of truth for your queries. E.g. one query - one file.

- *Static analysis*. Keep your queries in great shape and prevent stupid bugs.

- *Code review*. Don't hesitate to show your queries to your colleague, DBA, analyst, or someone in the business. And your queries will become clearer, faster, safer, and more valuable.

- *Tests*. Make sure your queries work with the right data.

- *Automate* it all.
