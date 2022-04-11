writeCode.

Write code to execute below expressions.

1. Create a database named `blog`.
2. Create a collection called 'articles'.
3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

4. Find all the articles using `db.COLLECTION_NAME.find()`
5. Find a document using \_id field.
6. 1. Find documents using title
7. 2. Find documents using author's name field.
8. Find document using a specific tag.

9. Update title of a document using its \_id field.
10. Update a author's name using article's title.
11. rename details field to description from all articles in articles collection.
12. Add additional tag in a specific document.

13. Update an article's title using $set and without $set.

- Write the differences here ?

13. find an article using title and increment it's auhtor's age by 5.

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
- Update user with extra golf field in sports array whose name is "Steve Ortega".
- Find all users who play either 'football' or 'cricket'.
- Find all users whose name includes 'ri' in their name.


```mongo
Last login: Mon Apr 11 10:16:33 on console
sakshamgarg@sakshams-MacBook-Pro ~ % mongo
MongoDB shell version v5.0.6
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("07e941a1-3a22-4be2-ae0c-c7adb01d1a3b") }
MongoDB server version: 5.0.6
================
Warning: the "mongo" shell has been superseded by "mongosh",
which delivers improved usability and compatibility.The "mongo" shell has been deprecated and will be removed in
an upcoming release.
For installation instructions, see
https://docs.mongodb.com/mongodb-shell/install/
================
---
The server generated these startup warnings when booting: 
        2022-04-11T10:17:18.249+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
---
---
        Enable MongoDB's free cloud-based monitoring service, which will then receive and display
        metrics about your deployment (disk utilization, CPU, operation statistics, etc).

        The monitoring data will be available on a MongoDB website with a unique URL accessible to you
        and anyone you share the URL with. MongoDB may use this information to make product
        improvements and to suggest MongoDB products and deployment options to you.

        To enable free monitoring, run the following command: db.enableFreeMonitoring()
        To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
---
> sb
uncaught exception: ReferenceError: sb is not defined :
@(shell):1:1
> db
test
> use blog
switched to db blog
> db.createCollection(articles);
uncaught exception: ReferenceError: articles is not defined :
@(shell):1:1
>  db.createCollection('articles');
{ "ok" : 1 }
> var articles = [
...     {
...         _id: 'some_random_id2',
...         title: 'Intro to nodejs',
...         details: 'This is nodejs article',
...         author: {
...           name: 'author1',
...           email: 'author1@gmail.com',
...           age: '35'
...         },
...         tags: ['js', 'mongo']
...       },
...       {
...         _id: 'some_random_id3',
...         title: 'Intro to mongo',
...         details: 'This is mongo article',
...         author: {
...           name: 'author2',
...           email: 'author2@gmail.com',
...           age: '34'
...         },
...         tags: ['js', 'mongo']
...       },
...       {
...         _id: 'some_random_id4',
...         title: 'Intro to xpress',
...         details: 'This is xpress article',
...         author: {
...           name: 'author3',
...           email: 'author3@gmail.com',
...           age: '32'
...         },
...         tags: ['js', 'mongo']
...       },
...       {
...         _id: 'some_random_id5',
...         title: 'Intro to html',
...         details: 'This is html article',
...         author: {
...           name: 'author5',
...           email: 'author4@gmail.com',
...           age: '23'
...         },
...         tags: ['js', 'mongo']
...       }
... 
... ]
> db.articles.insertMany(articles);
{
	"acknowledged" : true,
	"insertedIds" : [
		"some_random_id2",
		"some_random_id3",
		"some_random_id4",
		"some_random_id5"
	]
}
> show collections
articles
> db.articles.count
function(query, options) {
    const cmd =
        Object.assign({count: this.getName(), query: this._massageObject(query || {})}, options);
    if (cmd.readConcern) {
        cmd.readConcern = {level: cmd.readConcern};
    }
    const res = this._db.runReadCommand(cmd);
    if (!res.ok) {
        throw _getErrorWithCode(res, "count failed: " + tojson(res));
    }
    return res.n;
}
> db.articles.count
function(query, options) {
    const cmd =
        Object.assign({count: this.getName(), query: this._massageObject(query || {})}, options);
    if (cmd.readConcern) {
        cmd.readConcern = {level: cmd.readConcern};
    }
    const res = this._db.runReadCommand(cmd);
    if (!res.ok) {
        throw _getErrorWithCode(res, "count failed: " + tojson(res));
    }
    return res.n;
}
> db.articles.find().pretty
function() {
    this._prettyShell = true;
    return this;
}
> db.article.find()
> db.article.find()
> db.articles.find()
{ "_id" : "some_random_id2", "title" : "Intro to nodejs", "details" : "This is nodejs article", "author" : { "name" : "author1", "email" : "author1@gmail.com", "age" : "35" }, "tags" : [ "js", "mongo" ] }
{ "_id" : "some_random_id3", "title" : "Intro to mongo", "details" : "This is mongo article", "author" : { "name" : "author2", "email" : "author2@gmail.com", "age" : "34" }, "tags" : [ "js", "mongo" ] }
{ "_id" : "some_random_id4", "title" : "Intro to xpress", "details" : "This is xpress article", "author" : { "name" : "author3", "email" : "author3@gmail.com", "age" : "32" }, "tags" : [ "js", "mongo" ] }
{ "_id" : "some_random_id5", "title" : "Intro to html", "details" : "This is html article", "author" : { "name" : "author5", "email" : "author4@gmail.com", "age" : "23" }, "tags" : [ "js", "mongo" ] }
> 

```
