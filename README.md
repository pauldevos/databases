# Databases


## Postgres Clients for JavaScript
- [node-postgres](https://node-postgres.com/)
- [postgres](https://github.com/porsager/postgres)
- [sequelize](https://github.com/sequelize/sequelize)
- [Objection.js - An SQL-friendly ORM for Node.js](https://vincit.github.io/objection.js/)
- [typeorm](https://github.com/typeorm/typeorm)

These are just easy to grab a list of files and load into postgres. There is a COPY command executed via CLI/bash to which can be used and this is used for BULK loads by Data Analysts/Engineers. But that is often wrapped in a Python module called "subprocess" or "os" which executes it as a bash command. I'm not as familiar with using JS (e.g. Node?) for API development, but I imagine whichever ORM you find is best for API development would be the best tool to load data into the Postgres database.


### Understanding Indexes
1. Bitmap Indexes
  - https://richardstartin.github.io/posts/how-a-bitmap-index-works
2. JSONB Indexes
  - [unleash-the-power-of-storing-json-in-postgres](https://rollout.io/blog/unleash-the-power-of-storing-json-in-postgres/)
  - [overview-json-capabilities-within-postgresql](https://severalnines.com/database-blog/overview-json-capabilities-within-postgresql)
3. B-tree Indexes
  - [https://www.qwertee.io/blog/postgresql-b-tree-index-explained-part-1/](postgresql-b-tree-index-explained)
  - 
