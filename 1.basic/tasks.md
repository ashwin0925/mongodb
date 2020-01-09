#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..

use sports

2. list all databases present in local mongod server.
// Answer here..

show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
use sports

db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

db.cricket.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.cricket.insert({name:"kumar", age:25, email:"kum@gmail.com", state:"karnataka", auction_price:200000})
db.cricket.insert({name:"ash", age:25, email:"ashkum@gmail.com", state:"karnataka", auction_price:150000})

db.football.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.football.insert({name:"ash", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.football.insert({name:"kumar", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})

db.TT.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.TT.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.TT.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})



5. list all collections in sports database.

show collections

6. rename `TT` collection to `tennis`.

db.TT.renameCollections('tennis')

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection('khokho',{capped:true, size:4000, max:3})

db.khokho.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.khokho.insert({name:"kumar", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})
db.khokho.insert({name:"ash", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})

it takes only 3 documents
db.khokho.insert({name:"ashwin", age:25, email:"ash@gmail.com", state:"karnataka", auction_price:250000})

8. check whether a collection is capped or not?

db.khokho.isCapped()

9. remove all documents from `football` collection.

db.football.remove({})

10. delete cricket collection completely.

db.cricket.drop()

11. rename database sports to games

db.copyDatabase("sports","games")

12. delete sports database.
use sports
db.dropDatabase()
