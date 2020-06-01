# Databases




## Postgres Clients for JavaScript
- [node-postgres](https://node-postgres.com/)
- [postgres](https://github.com/porsager/postgres)
- [sequelize](https://github.com/sequelize/sequelize)
- [Objection.js - An SQL-friendly ORM for Node.js](https://vincit.github.io/objection.js/)
- [typeorm](https://github.com/typeorm/typeorm)

These are just easy to grab a list of files and load into postgres. There is a COPY command executed via CLI/bash to which can be used and this is used for BULK loads by Data Analysts/Engineers. But that is often wrapped in a Python module called "subprocess" or "os" which executes it as a bash command. I'm not as familiar with using JS (e.g. Node?) for API development, but I imagine whichever ORM you find is best for API development would be the best tool to load data into the Postgres database.


### Understanding Indexes
Here's a couple videos which give a pretty thorough rundown of indexes:
1. [PostgreSQL Indexing : How, why, and when](https://www.youtube.com/watch?v=clrtT_4WBAw)
2. [Things every developer absolutely, positively needs to know about database indexing - Kai Sassnowski](https://www.youtube.com/watch?v=HubezKbFL7E)

Only attempt to watch these if you're really interested in understanding indexes. I think, if the interest isn't there, the content can be a bit dry. Otherwise, perhaps read a quick perusable of these. The "big idea" is for those who understand NoSQL databasees and "key-value" ideas, the indexes will help you find similar keys in the data. Often times for relational data or for an API pulling data for a specific user. 

1. Bitmap Indexes
  - https://richardstartin.github.io/posts/how-a-bitmap-index-works
2. JSONB Indexes
  - [unleash-the-power-of-storing-json-in-postgres](https://rollout.io/blog/unleash-the-power-of-storing-json-in-postgres/)
  - [overview-json-capabilities-within-postgresql](https://severalnines.com/database-blog/overview-json-capabilities-within-postgresql)
3. B-tree Indexes
  - [https://www.qwertee.io/blog/postgresql-b-tree-index-explained-part-1/](postgresql-b-tree-index-explained)
4. Covered Indexes
  - [why-covering-indexes-are-incredibly-helpful](https://info.crunchydata.com/blog/why-covering-indexes-are-incredibly-helpful)
  
Ok, how about for some of the fun stuff. Actually playing with the language (syntax) and doing things.

### SQL Tutorials
- https://www.w3schools.com/sql/default.asp
- https://www.codecademy.com/learn/learn-sql
- https://sqlzoo.net/
- https://mode.com/sql-tutorial/

  
### SQL JOINS
![](image.png)
 
  
### Full Text Search in Postgres (Optional)
I'm not advocating for Search to be done in Postgres. This is more about the flexibility it offers and if you have smaller projects where you don't want to dedicate something like an ElasticSearch cluster to search. And it's a feature within Postgres you can use and has been fairly productive for many on a reasonable scale.

- [Official Postgres Documentation: Full Text Search](https://www.postgresql.org/docs/12/textsearch.html)
