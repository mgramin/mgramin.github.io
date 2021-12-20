---
title: "Cloudy with a chance of databases"
date: 2021-12-20T12:56:38+03:00
draft: false
tags: ['databases', 'cloud']
---

Michael Stonebraker is a live legend, godfather of databases, relational patriarch, Miles Davis in the database World. He stood at the database roots in 70 and to this day he stay on the bleeding edge of a data technologies. Today we will review his keynote "The cloud in your feature" from online conference [Postgres Build 2021](https://www.postgresbuild.com/registration-talks).

### All goes to the clouds
When you try to hide your hardware, wires and pipes under the floor in central London or Franfurkt, cloud guys from Microsoft Azure box up data centers in srandard 40 foot shipping containers and drop them around the World in places with cheap power. Guess who will win? On-Premise data centers is very expensive, but a cloud solutions became more cheaper and cheaper everyday. You have no chance to wins this guys.

### Divide compute and storage systems
Cloud companies provides amazing elasticity for you bussines. E.g. in Black Friday days you can upgrade cluster capacity of your e-commerce systems and makes money. In weekdays you can downgrade cluster, even to zero, and saves your money. Unfourtanly in a classical database architecture a compute subsystem and a storage subsystem traditionaly strong bonded, and It devalues cloud capabilities. But new data warehous systems, such as Snowflake, successfuly solves this architecture problem, e.g. using S3 for storage.

### Long live stored procedures
In last decade traditionaly server busines code on database side was considered as an ancient and not scalable architectural solution. But when you can devides DB storage system from compute system and you can scale this ones separately and independency, than a stored procedure becomes simple, modern and high perfomance solution again. Your bussines code and your bussines data are now together and forever.
