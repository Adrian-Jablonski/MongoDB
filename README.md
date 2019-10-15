# MongoDB
MongoDB Course

## Installing and Running MongoDB on a Windows Machine
Download the MongoDB installer file from the downloads section of the MongoDB website.

Find the dowloaded .msi file in the Windows Explorer. Double click the file and follow the prompts to install Mongo. Note: unless you specify a custom directory Mongo is most likely installed in the C:\mongodb directory**. However, based on settings on your machine Mongo may be installed other places. For example, C:\Program Files\MongoDB\Server\3.2. Additionally, you may find MongoDB in the add/remove programs menu.

Create the directory where MongoDB will store it’s files. From the command prompt run md \data\db. This is the default location. However, other locations can be specified using the --dbpath parameter. See the Mongo docs for more information.

Start the mongodb daemon by running C:\mongodb\bin\mongod.exe in the Command Prompt. Or by running, C:\path\to\mongodb\bin\mongod.exe. On my PC (C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe)

Connect to MongoDB using the Mongo shell While the MongoDB daemon is running, from a different Command prompt window run C:\mongodb\bin\mongo.exe. On my PC (C:\Program Files\MongoDB\Server\4.2\bin\mongo.exe)

## Using Mongo Shell
show dbs    // lists databases

use mongoBasics     // Switches to a database called mongoBasics (creates the database if it does not exist)

 db.post.insert({title: "Hello"})   // inserts data into database

 db.post.find()     // lists all documents created in a collection

 load('D:/Computer Programming Education/MongoDB/seed.js')  // used to load the seed.js DB script

 db.posts.find().limit(2)   // returns the first 2 users

 var post = db.posts.find()[1];
 post.title     // returns "I love the holidays"