writeCode


Write command to

- List collections from a database.
- create a new collection in your country database which you created recently.

Write code to:-

- crate a database named `weather`
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
- create a simple collection named `humidity`
- check whether `temperature` collection is capped or not ?
- Delete `humidity` collection and then the entire database(weather).
```mongoDB
uncaught exception: ReferenceError: mongo is not defined :
@(shell):1:1
> use weather
switched to db weather
> db
weather
> show collection
uncaught exception: Error: don't know how to show [collection] :
shellHelper.show@src/mongo/shell/utils.js:1211:11
shellHelper@src/mongo/shell/utils.js:838:15
@(shellhelp2):1:1
> show collections
> show dbs
admin   0.000GB
config  0.000GB
india   0.000GB
local   0.000GB
> db.dropDatabase()
{ "ok" : 1 }
> use india
switched to db india
> db.createCollection('delhi')
{
	"ok" : 0,
	"errmsg" : "Collection already exists. NS: india.delhi",
	"code" : 48,
	"codeName" : "NamespaceExists"
}
> use weather
switched to db weather
> db.createCollection('temprature',{cabbed: tuue,sized: 1024,max:3})
uncaught exception: ReferenceError: tuue is not defined :
@(shell):1:35
> db.createCollection('temprature',{capped: tuue,sized: 1024,max:3})
uncaught exception: ReferenceError: tuue is not defined :
@(shell):1:35
> db.createCollection('temprature',{capped: true,size: 1024,max:3})
{ "ok" : 1 }
> show collections
temprature
> db.temprature.insertMany([{delhi:34},{himachal:21},{kashmir:15}]);
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("6251c7c9e46a1f442b1f276c"),
		ObjectId("6251c7c9e46a1f442b1f276d"),
		ObjectId("6251c7c9e46a1f442b1f276e")
	]
}
> db.temprature.find()
{ "_id" : ObjectId("6251c7c9e46a1f442b1f276c"), "delhi" : 34 }
{ "_id" : ObjectId("6251c7c9e46a1f442b1f276d"), "himachal" : 21 }
{ "_id" : ObjectId("6251c7c9e46a1f442b1f276e"), "kashmir" : 15 }
> db.temprature.insert({chennai:50});
WriteResult({ "nInserted" : 1 })
> db.temprature.find()
{ "_id" : ObjectId("6251c7c9e46a1f442b1f276d"), "himachal" : 21 }
{ "_id" : ObjectId("6251c7c9e46a1f442b1f276e"), "kashmir" : 15 }
{ "_id" : ObjectId("6251c7f4e46a1f442b1f276f"), "chennai" : 50 }
> db.createCollection('Humidity');
{ "ok" : 1 }
> show collections
Humidity
temprature
> db.temprature.isCapped()
true
> db.Humidity.isCapped();
false
> db.Humidity.drop();
true
> show collections
temprature
> db
weather
> db.drawDatabase()
uncaught exception: TypeError: db.drawDatabase is not a function :
@(shell):1:1
> db.drawDatabase()
uncaught exception: TypeError: db.drawDatabase is not a function :
@(shell):1:1
> db.dropDatabase()
{ "ok" : 1 }
> show collections
> 
```
