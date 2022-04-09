writeCode

Write code to:-


- create a database named `sports`.
- list all databases present in local mongod server.
- create 3 collections named `cricket`, `football`, `TT` in sports databse.
- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
- list all collections in sports database.
- rename `TT` collection to `tennis`.
- create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and see what happens?
- check whether a collection is capped or not?
- drop all documents from `football` collection.
- delete cricket collection completely.
- delete sports database.
- check which database you are connected to ?
- connect to test database
- ```mongo
> db
sports
> db.createCollection('cricket');
{ "ok" : 1 }
> show collections
cricket
> var players =[
... {
...     name: "player1",
...     email: 'iplyer1@CSSMediaRule.com',
...     bid_price: '$40',
...     age: '21'
... },
... {
...     name: "player2",
...     email: 'iplyer2@CSSMediaRule.com',
...     bid_price: '$40',
...     age: '22'
... },
... {
...     name: "player3",
...     email: 'iplyer3@CSSMediaRule.com',
...     bid_price: '$43',
...     age: '23'
... },
... {
...     name: "player4",
...     email: 'iplyer4@CSSMediaRule.com',
...     bid_price: '$44',
...     age: '24'
... }
... 
... ]
> players
[
	{
		"name" : "player1",
		"email" : "iplyer1@CSSMediaRule.com",
		"bid_price" : "$40",
		"age" : "21"
	},
	{
		"name" : "player2",
		"email" : "iplyer2@CSSMediaRule.com",
		"bid_price" : "$40",
		"age" : "22"
	},
	{
		"name" : "player3",
		"email" : "iplyer3@CSSMediaRule.com",
		"bid_price" : "$43",
		"age" : "23"
	},
	{
		"name" : "player4",
		"email" : "iplyer4@CSSMediaRule.com",
		"bid_price" : "$44",
		"age" : "24"
	}
]
> db.cricket.insertMany(players)
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("6251deb3e46a1f442b1f2770"),
		ObjectId("6251deb3e46a1f442b1f2771"),
		ObjectId("6251deb3e46a1f442b1f2772"),
		ObjectId("6251deb3e46a1f442b1f2773")
	]
}
> db.cricket.find()
{ "_id" : ObjectId("6251deb3e46a1f442b1f2770"), "name" : "player1", "email" : "iplyer1@CSSMediaRule.com", "bid_price" : "$40", "age" : "21" }
{ "_id" : ObjectId("6251deb3e46a1f442b1f2771"), "name" : "player2", "email" : "iplyer2@CSSMediaRule.com", "bid_price" : "$40", "age" : "22" }
{ "_id" : ObjectId("6251deb3e46a1f442b1f2772"), "name" : "player3", "email" : "iplyer3@CSSMediaRule.com", "bid_price" : "$43", "age" : "23" }
{ "_id" : ObjectId("6251deb3e46a1f442b1f2773"), "name" : "player4", "email" : "iplyer4@CSSMediaRule.com", "bid_price" : "$44", "age" : "24" }
> db.cricket.find().pretty()
{
	"_id" : ObjectId("6251deb3e46a1f442b1f2770"),
	"name" : "player1",
	"email" : "iplyer1@CSSMediaRule.com",
	"bid_price" : "$40",
	"age" : "21"
}
{
	"_id" : ObjectId("6251deb3e46a1f442b1f2771"),
	"name" : "player2",
	"email" : "iplyer2@CSSMediaRule.com",
	"bid_price" : "$40",
	"age" : "22"
}
{
	"_id" : ObjectId("6251deb3e46a1f442b1f2772"),
	"name" : "player3",
	"email" : "iplyer3@CSSMediaRule.com",
	"bid_price" : "$43",
	"age" : "23"
}
{
	"_id" : ObjectId("6251deb3e46a1f442b1f2773"),
	"name" : "player4",
	"email" : "iplyer4@CSSMediaRule.com",
	"bid_price" : "$44",
	"age" : "24"
}
> db.football.insertMany(players)
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("6251df3ee46a1f442b1f2774"),
		ObjectId("6251df3ee46a1f442b1f2775"),
		ObjectId("6251df3ee46a1f442b1f2776"),
		ObjectId("6251df3ee46a1f442b1f2777")
	]
}
> db.TT.insertMany(players)
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("6251df4ee46a1f442b1f2778"),
		ObjectId("6251df4ee46a1f442b1f2779"),
		ObjectId("6251df4ee46a1f442b1f277a"),
		ObjectId("6251df4ee46a1f442b1f277b")
	]
}
> show collections
TT
cricket
football
> db.TT.renameCollection('TableTennis');
{ "ok" : 1 }
> show collections
TableTennis
cricket
football
> db.createcollection('khokho',{capped: true,size:2040,max: 3})
uncaught exception: TypeError: db.createcollection is not a function :
@(shell):1:1
> db.createCollection('khokho',{capped: true,size:2040,max: 3})
{ "ok" : 1 }
> db.khokho.insertMany(players)
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("6251e0ede46a1f442b1f277c"),
		ObjectId("6251e0ede46a1f442b1f277d"),
		ObjectId("6251e0ede46a1f442b1f277e"),
		ObjectId("6251e0ede46a1f442b1f277f")
	]
}
> show collections
TableTennis
cricket
football
khokho
> db.khokho.find()
{ "_id" : ObjectId("6251e0ede46a1f442b1f277d"), "name" : "player2", "email" : "iplyer2@CSSMediaRule.com", "bid_price" : "$40", "age" : "22" }
{ "_id" : ObjectId("6251e0ede46a1f442b1f277e"), "name" : "player3", "email" : "iplyer3@CSSMediaRule.com", "bid_price" : "$43", "age" : "23" }
{ "_id" : ObjectId("6251e0ede46a1f442b1f277f"), "name" : "player4", "email" : "iplyer4@CSSMediaRule.com", "bid_price" : "$44", "age" : "24" }
> db.khokho.find().preety
> > db.khokho.find().preety
uncaught exception: SyntaxError: expected expression, got '>' :
@(shell):1:0
> db.khokho.count()
3
> show collections
TableTennis
cricket
football
khokho
> db.khokho.isCapped()
true
> db.TableTennis.isCapped()
false
> db.football.find()
{ "_id" : ObjectId("6251df3ee46a1f442b1f2774"), "name" : "player1", "email" : "iplyer1@CSSMediaRule.com", "bid_price" : "$40", "age" : "21" }
{ "_id" : ObjectId("6251df3ee46a1f442b1f2775"), "name" : "player2", "email" : "iplyer2@CSSMediaRule.com", "bid_price" : "$40", "age" : "22" }
{ "_id" : ObjectId("6251df3ee46a1f442b1f2776"), "name" : "player3", "email" : "iplyer3@CSSMediaRule.com", "bid_price" : "$43", "age" : "23" }
{ "_id" : ObjectId("6251df3ee46a1f442b1f2777"), "name" : "player4", "email" : "iplyer4@CSSMediaRule.com", "bid_price" : "$44", "age" : "24" }
> db.football.remove({})
WriteResult({ "nRemoved" : 4 })
> db.cricket.drop()
true
> show Collections
uncaught exception: Error: don't know how to show [Collections] :
shellHelper.show@src/mongo/shell/utils.js:1211:11
shellHelper@src/mongo/shell/utils.js:838:15
@(shellhelp2):1:1
> show collections
TableTennis
football
khokho
> db
sports
> db.dropDatabase()
{ "ok" : 1 }
> sb
uncaught exception: ReferenceError: sb is not defined :
@(shell):1:1
> show dbs
admin   0.000GB
config  0.000GB
india   0.000GB
local   0.000GB
> db
sports
> use test
switched to db test
> db
test
> 
```
