#### write commands for following mongodb opertaions

1. create a database named `sports`
   // Answer here ..
   use sports

2. list all databases present in local mongod server.
   // Answer here..
   show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
   db.createCollection('cricket')
   db.createCollection('football')
   db.createCollection('TT')

4) add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
   db.cricket.insert({name:'SSB',age:25,email:"sudhan@gmail.com",state:"odisha",auction_price:100},{name:"hsb",age:25,,email:"himan@gmail.com",state:"maharastra",auction_price:200},
   {name:"ss",age:25,email:"ss@gmail.com",state:"haryana",auction_price:50})

db.football.insert({
name:'SSB',age:25,email:"sudhan@gmail.com",state:"odisha",auction_price:100},
{name:"hsb",age:25,,email:"himan@gmail.com",state:"maharastra",auction_price:200},
{name:"ss",age:25,email:"ss@gmail.com",state:"haryana",auction_price:50})

db.TT.insert({name:'SSB',age:25,email:"sudhan@gmail.com",state:"odisha",auction_price:100},{name:"hsb",age:25,,email:"himan@gmail.com",state:"maharastra",auction_price:200},
{name:"ss",age:25,email:"ss@gmail.com",state:"haryana",auction_price:50})

5. list all collections in sports database.
   show collections

6. rename `TT` collection to `tennis`.
   db.TT.renameCollection('tennis')

7) create a capped collection called `khokho` which should have max 3 documents.
   db.createCollection("khokho", {capped: true, size: 100000, max: 3})
   Try inserting more than 3 and output the result here ?
   db.khokho.insert({
   name:'SSB',age:25},
   {name:"hsb",age:25},
   {name:"ss",age:25})

db.khokho.insert({name:'jagu',age:25})
db.khokho.insert({name:'balu',age:25})
output:

{ "\_id" : ObjectId("5f15390a2cabcd4cf90e8260"), "name" : "SSB", "age" : 25 }
{ "\_id" : ObjectId("5f1539182cabcd4cf90e8261"), "name" : "jagu", "age" : 25 }
{ "\_id" : ObjectId("5f1539232cabcd4cf90e8262"), "name" : "balu", "age" : 25 }

8. check whether a collection is capped or not?
   db.TT.isCapped()

9) remove all documents from `football` collection.
   db.football.remove({})

10. delete cricket collection completely.
    db.cricket.drop()

11. rename database sports to games

12. delete sports database.
    use sports
    db.dropDatabase()
