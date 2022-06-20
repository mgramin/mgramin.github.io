---
title: "Stop coding please or The Fourth rule of Codd"
date: 2022-03-09T14:40:01+03:00
draft: false
tags: ['SQL', 'database-as-code']
---

To successfully work with any database system, we need a bunch of different auxiliary tools, such as IDE, DB-managers, perfomance tuning and monitoring systems, data visualization and documentation tools and many others. Indeed, there is a monstrous number of different DB tools for working with different databases. And it's a big problem, especially if you use several DBMS at once in your project, it can turn into a real "tools hell".

<!-- separate for WEB, separate for CLI etc -->
<!-- SQL is a Value, all other is a boilerplate -->

## `M x N` Problem

And it looks like famous `M x N` problem - for M tools (such as editors, IDE, perfomance analyzers, etc) to support N systems (such as DBMS's, program languages, etc), we need `M x N` solutions.

But LSP provides single universal protocol and turns `M x N` problem to an `M + N` problem:

> With the introduction of LSP, the editor only needed to implement support for the Language Server Protocol. Once it did, anyone who makes a language server (following the LSP standards) can be seamlessly integrated with the editor, without the editor ever intelligently "knowing" what language it is working with!


## SQL as a Protocol

<!-- between data and tools -->

But in the database world we already have universal integration point, and it is SQL.
<!-- https://www.timescale.com/blog/why-sql-beating-nosql-what-this-means-for-future-of-data-time-series-database-348b777b847a/ -->

<!-- What we need is an interface that allows pieces of this stack to communicate with one another. Ideally something already standardized in the industry. Something that would allow us to swap in/out various layers with minimal friction. -->

> That is the power of SQL. Like IP, SQL is a universal interface.
But SQL is in fact much more than IP. Because data also gets analyzed by humans. And true to the purpose that SQL’s creators initially assigned to it, SQL is readable.

## Back to the 80s

The 80s were truly a golden times. Metallica released their debut album in '83, [Exodus](https://en.wikipedia.org/wiki/Exodus_(American_band)) recorded their debut in '84 and Edgar Codd published his "[Twelve Commandments](https://en.wikipedia.org/wiki/Codd%27s_12_rules)" in '85. Most of these rules are still relevant today and not only for relational databases, expecially Rule 4 "Dynamic online catalog based on the relational model":

> The data base description is represented at the logical level in the same way as ordinary data, so that authorized users can apply the same relational language to its interrogation as they apply to the regular data.

What does this mean for us? 

<!-- We can get iformation about DB's health and condition (metadata) the same method like a normal data `select * from ...` -->

<!-- In this way in relational DB Everything is a Data -->


## Documentation

SQL + incredibly powerful Twitter Bootstrap framework (web standard de facto)

```sql
select c.table_schema
     , c.table_name
     , c.column_name
     , ...
  from pg_tables t
  join columns c on c.table_schema = t.schemaname
                and c.table_name = t.tablename
 where table_schema = %(schema_name)s
```

## Charts

```sql
select table_name
     , sum(raw_total_size) as total_size
  from (select table_name
             , rank() over (order by raw_total_size desc) as rank
             , raw_total_size
          from (select table_name
                     , pg_total_relation_size(quote_ident(table_name)) as raw_total_size
                  from information_schema.tables
                 where table_schema = %(schema_name)s ) as base) as agg
 where rank <= %(max_table_count)s
 group by table_name
```

![largest-tables-quickchart](/stop-coding-please/largest-tables-quickchart.png)

## Metrics

## Diagrams

Actually we need only information about columns/tables (already have) and relationships between tables, and it is easy (from `information_schema`):

```sql
select distinct 
       ccu.table_name as main_table
     , tc.table_name as slave_table
  from table_constraints as tc
  join key_column_usage as kcu on tc.constraint_name = kcu.constraint_name
  join constraint_column_usage as ccu on ccu.constraint_name = tc.constraint_name
 where tc.constraint_type = 'FOREIGN KEY'
```

![stop-coding-please](/stop-coding-please/er-diagram-plantuml.png)



<!-- There are many necessary commons tools -->
