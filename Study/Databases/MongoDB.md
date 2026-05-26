## Basic Commands

- **Start MongoDB Server**: `mongod`
- **Connect to MongoDB**: `mongo`

## Database Operations

- **Show All Databases**: `show dbs`
- **Use a Database**: `use <database_name>`
- **Create a Database**: `use <database_name>`
- **Drop a Database**: `db.dropDatabase()`

## Collection Operations

- **Show Collections**: `show collections`
- **Create a Collection**: `db.createCollection('<collection_name>')`
- **Drop a Collection**: `db.<collection_name>.drop()`

## Document Operations

- **Insert a Document**: `db.<collection_name>.insert({<field1>: <value1>, <field2>: <value2>, ...})`
- **Find Documents**: 
  - `db.<collection_name>.find()`
  - `db.<collection_name>.find({<field>: <value>})`
- **Update Documents**: 
  - `db.<collection_name>.update({<query>}, {<update>})`
  - `db.<collection_name>.update({<query>}, {<update>}, {multi: true})`
- **Remove Documents**: 
  - `db.<collection_name>.remove({<field>: <value>})`
  - `db.<collection_name>.remove({})` (Remove all documents)

## Query Operators

- **Equality**: `{<field>: <value>}`
- **Less Than**: `{<field>: {$lt: <value>}}`
- **Greater Than**: `{<field>: {$gt: <value>}}`
- **Logical AND**: `{<field1>: <value1>, <field2>: <value2>}`
- **Logical OR**: `{$or: [{<field1>: <value1>}, {<field2>: <value2>}]}`

## Indexing

- **Create an Index**: `db.<collection_name>.createIndex({<field>: <1|-1>})`
- **List Indexes**: `db.<collection_name>.getIndexes()`
- **Drop an Index**: `db.<collection_name>.dropIndex('<index_name>')`

## Aggregation

- **Group Documents**: 
  ```javascript
  db.<collection_name>.aggregate([
    {$group: {_id: '<field>', total: {$sum: '<field>'}}}
  ])
  ```

## Backup and Restore

- **Backup**: `mongodump --db <database_name> --out <directory_path>`
- **Restore**: `mongorestore --db <database_name> <directory_path>`

## User Management

- **Create a User**: 
  ```javascript
  use admin
  db.createUser({
    user: "<username>",
    pwd: "<password>",
    roles: [{role: "readWrite", db: "<database_name>"}]
  })
  ```
- **Authenticate**: `mongo -u <username> -p <password> --authenticationDatabase <database_name>`
- **Drop a User**: `db.dropUser("<username>")`