writeCode

Write code to:-


- create a database named `mountains`
- a collection inside that database named `himalayas`
- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`

- insert multiple document using insertMany command
- find all documents from mountains
- find a single document using name

```mongo
> db.collections
test.collections
> use mountains
switched to db mountains
> db.createCollection('himalayas')
{ "ok" : 1 }
> show collections
himalayas
> show db
uncaught exception: Error: don't know how to show [db] :
shellHelper.show@src/mongo/shell/utils.js:1211:11
shellHelper@src/mongo/shell/utils.js:838:15
@(shellhelp2):1:1
> db.himalayas.insert({name: 'Dhauldhar range', height: '4000 mtrs'});
WriteResult({ "nInserted" : 1 })
> show collections
himalayas
> db.himalayas.find()
{ "_id" : ObjectId("6253007258cdda49a34227e4"), "name" : "Dhauldhar range", "height" : "4000 mtrs" }
> db.himalays.find().pretty
function() {
    this._prettyShell = true;
    return this;
}
> var himalayas= [ ]
> 
```
