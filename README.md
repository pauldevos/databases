# Databases




## Postgres Clients for JavaScript
- [node-postgres](https://node-postgres.com/)
- [postgres](https://github.com/porsager/postgres)
- [sequelize](https://github.com/sequelize/sequelize)
- [Objection.js - An SQL-friendly ORM for Node.js](https://vincit.github.io/objection.js/)
- [typeorm](https://github.com/typeorm/typeorm)

These are just easy to grab a list of files and load into postgres. There is a COPY command executed via CLI/bash to which can be used and this is used for BULK loads by Data Analysts/Engineers. But that is often wrapped in a Python module called "subprocess" or "os" which executes it as a bash command. I'm not as familiar with using JS (e.g. Node?) for API development, but I imagine whichever ORM you find is best for API development would be the best tool to load data into the Postgres database.

  
Ok, how about for some of the fun stuff. Actually playing with the language (syntax) and doing things.

### SQL Tutorials
- https://www.w3schools.com/sql/default.asp
- https://www.codecademy.com/learn/learn-sql
- https://www.postgresqltutorial.com/
- https://sqlzoo.net/
- https://mode.com/sql-tutorial/


### SQL Query Format

```SQL
-- an example query
SELECT
  u.id,
  u.first_name,
  u.last_name,
  u.birthdate,
  p.article_id,
  AVG(p.article_length) as avg_length_articles,
  SUM(CASE WHEN 'basketball' in p.article_blob THEN 1 ELSE 0 END) as basketball_articles,
  COUNT(*) as total_articles
FROM users u
LEFT JOIN posts p
  ON u.id = p.author_id
WHERE
  u.active = 1
  AND p.is_draft = 0
  AND p.published_date > '01/01/2020'
ORDER BY
  COUNT(*) DESC,
  u.last_name


-- Basic Format
SELECT
-- columns
-- aggregates
-- window functions
FROM
-- JOINS -- LEFT, RIGHT, INNER, OUTER, CROSS, UNION, UNION ALL
WHERE -- conditional filters for your "RESULT SETS", filtered at runtime of the query
GROUP BY
-- use this when you use AGGREGATES in the SELECT part, in effect is is a Map-Reduce Key-mapper for the aggregates
ORDER BY
-- ASC by default, DESC if you wish
HAVING
-- this is POST runtime, after the results have come through, you can FILTER again, e.g. HAVING articles_authored > 3

```



### SQL JOINS


------

![sql-joins-guide.jpg](sql-joins-guide.jpg)
 
------

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
  
### Official Postgres Documentation (Parts you might read first, but are a bit dryer than most tutorials)
- [The SQL Syntax](https://www.postgresql.org/docs/12/sql-syntax.html)
- [Postgres functions](https://www.postgresql.org/docs/12/functions.html)
- [Queries](https://www.postgresql.org/docs/12/queries.html)
- [Data Manipulation or DML commands](https://www.postgresql.org/docs/12/dml.html)
- [Data Definitions or DDL commands](https://www.postgresql.org/docs/12/ddl.html)
- [Data Types](https://www.postgresql.org/docs/12/datatype.html)
  
  
  
-------

### Full Text Search in Postgres (Optional)
I'm not advocating for Search to be done in Postgres. This is more about the flexibility it offers and if you have smaller projects where you don't want to dedicate something like an ElasticSearch cluster to search. And it's a feature within Postgres you can use and has been fairly productive for many on a reasonable scale.

- [Official Postgres Documentation: Full Text Search](https://www.postgresql.org/docs/12/textsearch.html)
