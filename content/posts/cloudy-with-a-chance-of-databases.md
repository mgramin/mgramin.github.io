---
title: "Cloudy with a chance of databases"
date: 2021-12-20T12:56:38+03:00
draft: false
tags: ['databases', 'cloud']
---

Michael Stonebraker is a live legend, godfather of databases, relational patriarch, Miles Davis in the database World. He stood at the database roots in the 70s and to this day he stays on the bleeding edge of data technologies. Today we will review his keynote "The cloud in your feature" from an online conference [Postgres Build 2021](https://www.postgresbuild.com/registration-talks).

### All goes to the clouds
When you try to hide hardware, wires and pipes under the floor in your office in central London or Frankfurt, cloud guys from Microsoft Azure box up data centers in standard 40 foot shipping containers and drop them around the World in places with cheap power. Guess who will win? On-Premise data centers are very expensive, but cloud solutions become cheaper and cheaper everyday. You have no chance to win these guys.

### Divide compute and storage systems
Cloud companies provide amazing elasticity for your business. E.g. in Black Friday days you can upgrade the cluster capacity of your e-commerce systems and make money. In weekdays you can downgrade cluster, even to zero, and saves your money. Unfortunately in a classical database architecture a compute subsystem and a storage subsystem traditionally are strongly bonded, and It devalues cloud capabilities. But new data warehouse systems, such as Snowflake, successfully solves this architecture problem, e.g. using S3 for storage.

### Long live stored procedures
In the last decade traditionally server business code on the database side was considered as an ancient and not scalable architectural solution. But when you can divide a DB storage system from a compute system and you can scale this one's separately and independently, stored procedures become a simple, modern and high performance solution again. Your business code and your business data are now together and forever.
