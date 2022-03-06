---
title: "Database as Code"
date: 2022-02-27T14:40:01+03:00
draft: false
tags: ['SQL', 'database-as-code']
---

I have spent a lot of time working with various database systems. I was a SQL and PL/SQL developer on big distributed teams, writing tons of nontrivial SQL queries and implementing tons of complex and tricky business logic on the database side. Then I worked as a classical Java developer where we interacted with any databases through ORM, operating only JPA annotation and framework properties (hoping to find and turn on a "magic" parameter `fast=true`).

And all this time, I have had this feeling that database technologies (especially the part that is related to the comfort and speed of development) are far behind other IT areas (e.g. WEB, infrastructure, integrations, etc.). Working with databases remained slow, laborious, and very risky. 

And I'm not alone in this feeling. For example, the tagline of [dolt](https://www.dolthub.com) database (which provides Git options and MySQL API for your Data) also says about it:

> "Software development has come a long way in the last 30 years.
> Why is your database stuck in 1995?"


[Markus Winand](https://twitter.com/markuswinand) in his talk "[Modern SQL in Open Source and Commercial Databases](https://www.slideshare.net/MarkusWinand/modern-sql)" discusses the situation where most developers still use SQL-92 standard to this day:

> "Still Using Windows 3.1? So why stick to SQL-92?"

And now the most interesting. [Dan North](https://twitter.com/tastapod) in his eponymous [talk](https://speakerdeck.com/tastapod/arent-we-forgetting-someone) about DevOps things wonders:

> "Aren't we forgetting someone?"

And the right answer is: "Yes, we are forgetting about DBA's". Because DBA's are often separate geographically and organizationally, and databases don't fit into the DevOps story.

So let's take a look closer. The DevOps era brought to us "Everything as Code" philosophy, where any IT area might represent as a plain code, and we can work with it using standard tools and technologies (code editors, control version systems, CI/CD pipelines etc.). And yes, indeed, there are many "Everything as Code" realizations for many areas, for example:

- Pipeline as Code (`Jenkinsfile`, `.gitlab-ci.yml`, `settings.kts` in TeamCity)
- Infrastructure as Code (Kubernetes, Terraform, Ansible)
- Diagram as Сode (PlantUML, Graphviz, Mermaid)
- Documentation as Сode (Markdown, AsciiDoc)
- Tests as Code (Gatling, Cucumber)

But how about "Database as Code"? It was still a very exotic combination of words, and Dan North offers four simple rules for treating a database like Code:

- All changes scripted and automated
- All changes under version control
- Ability to release on demand
- DBA's integrated with Dev and Ops

It's been six years, and nowadays, it's hard to find a project that doesn't follow these rules (at least the first three). There are a lot of [database migration tools](https://github.com/mgramin/awesome-db-tools#migration-tools) and ways to integrate it with your VCS and your CI/CD pipeline. And it's really great.

However, I've always been interested in a few things:

- Database code is not only "scripts with changes". It's also DML and all kinds of SQL scripts
- In addition to DBA's, there are many kinds of data people who intensively work with databases and use SQL
- Is SQL still the main database language?

And I prepared an extended list of "Database as Code" rules:

- Treat your database or other storage system as a code
- All changes and operations with the database and all queries (ideally) against the database should be expressed as a plain old code
- Git (or anything else VCS) is a single source of truth for database code
- SQL actually is a main database language supported by almost all DBMS
- SQL is not a bytecode for your data and your database, it's a normal human-oriented program language ([why](/posts/sql-is-not-a-bytecode-for-data))
- SQL is designed not only for data, but also for metadata
- Database code is not only DDL and other migration scripts, DML and all kinds of SQL scripts too
- Database code is a normal code, and it also needs static analysis, code review (especially by DBA, analysts and business people), tests and automation of it all
- DBA's and data people should be integrated with Dev and Ops
- Ability to release on demand.

The original version of this list (as well as a list of related tools and resources) is hosted on [GitHub](https://github.com/mgramin/database-as-code). Feel free to create a PR and issues.
