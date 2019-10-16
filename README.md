# MongoDB
MongoDB Course

## Installing and Running MongoDB on a Windows Machine
Download the MongoDB installer file from the downloads section of the MongoDB website.

Find the dowloaded .msi file in the Windows Explorer. Double click the file and follow the prompts to install Mongo. Note: unless you specify a custom directory Mongo is most likely installed in the C:\mongodb directory**. However, based on settings on your machine Mongo may be installed other places. For example, C:\Program Files\MongoDB\Server\3.2. Additionally, you may find MongoDB in the add/remove programs menu.

Create the directory where MongoDB will store it’s files. From the command prompt run md \data\db. This is the default location. However, other locations can be specified using the --dbpath parameter. See the Mongo docs for more information.

Start the mongodb daemon by running C:\mongodb\bin\mongod.exe in the Command Prompt. Or by running, C:\path\to\mongodb\bin\mongod.exe. On my PC (C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe)

Connect to MongoDB using the Mongo shell While the MongoDB daemon is running, from a different Command prompt window run C:\mongodb\bin\mongo.exe. On my PC (C:\Program Files\MongoDB\Server\4.2\bin\mongo.exe)

## Mongo hacker
Used to highlight mongo syntax in the terminal

npm install -g mongo-hacker 

## Using Mongo Shell
show dbs    // lists databases

use mongoBasics     // Switches to a database called mongoBasics (creates the database if it does not exist)

 db.post.insert({title: "Hello"})   // inserts data into database

 db.post.find()     // lists all documents created in a collection

 load('D:/Computer Programming Education/MongoDB/seed.js')  // used to load the seed.js DB script

 db.posts.find().limit(2)   // returns the first 2 users

 var post = db.posts.find()[1];
 post.title     // returns "I love the holidays"

 db.posts.getIndexes()      // returns index

db.posts.createIndex({title: 1}, {})    // use 1 for ascending order or -1 for descending order


 db.posts.dropIndex('title_1')      // Deletes an index

### Querying collections
 db.posts.find({}, {body: false, description: false})    // returns documents without body and description field

 db.posts.find({}, {title: true})   // returns documents with title field and ID field only

 db.posts.find({title: "Parenting 101"})    // queries for post with a title of "Parenting 101"

 db.posts.find({$or: [{title: "Parenting 101"}, {title: "My Awesome Recipe!"}]})    // returns a post with a title of "Parenting 101" or "My Awesome Recipe!"

 ### Updating Data
 db.posts.update({author: ObjectId("5da64dde9294e2ca5574b317")}, {$set: {tags: ['foo', 'bar'], title: "I'm an Updated Title!"}})    // adds a new tag field and updates the title field

 ### Sorting data
 db.posts.find({}, {title:true}).sort({title: 1})   // sorts by title in ascending order 

 ### Pagination using sort and skip
 db.posts.find({}, {title:true}).sort({title: 1}).limit(2).skip(2)   // returns second page of results (results 3 - 4)

 ## MongoDB Drivers: 
 https://docs.mongodb.org/ecosystem/drivers/

 ## Sharding in Mongo: 
 https://docs.mongodb.org/manual/sharding/