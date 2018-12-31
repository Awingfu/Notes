# Getting Started with MongoDB

[MongoDB Setup Mac](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

## On Mac

1. use ```brew install mongodb```
2. make default /data/db directory with ```sudo mkdir -p /data/db```
3. give access to /data/db with ```sudo chmod 777 /data/db```
4. run ```mongod``` to initialize server (`control` + `C` to quit)
5. in another terminal, run ```mongo``` to connect

### Using shell

[MongoDB guide to databases/collections basics](https://docs.mongodb.com/manual/core/databases-and-collections/) 

* use ```show dbs``` to show databases in mongo
* use ```use <db name>``` to use a database (creates if does not exist)
* use ```db.createCollection('<collection name>')``` to create a collection
* use ```show collections``` to show collections
* use ```db.<collection name>.insert({key:value})``` to insert a BSON into a collection; the `id` field is automatically created
* use ```db.<collection name>.find()``` to list all items in a collection
    * can chain to ```db.<collection name>.find().pretty()``` to list prettier

## For NodeJS, MongooseJS

[MongooseJS Official Page](https://mongoosejs.com/)

