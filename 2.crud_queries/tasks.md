1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insert({title:"web design", description:"all about web design", author:{name:'alt', email:'contact@gmail', age:25} tags:['html', 'css']})

db.articles.insert({title:"software engineering", description:"for beginners", author:{name:'ashwin', email:'ashwin@gmail', age:25} tags:['html', 'js']})

db.articles.insert({title:"UI", description:"every thing about UI", author:{name:'kumar', email:'kumar@gmail', age:25} tags:['css', 'js']})


4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()

5. Find a document using _id field.

db.articles.find({"_id" : ObjectId("5e16d2443bef106a66807f3b")})

6. Find documents using title and author's name field.

db.articles.find({title:"web design", 'author.name':'alt'})

7. Find document using a specific tag.

db.articles.find({tags:'html'})

8. Update title of a document using its _id field.

db.articles.update({"_id" : ObjectId("5e16d2443bef106a66807f3b")}, {$set:{'title:"learn node"}})

9. Update a author's name using article's title.

db.articles.update({"title":"learn node"}, {$set:{'author.name':'altas'}})

10. rename details field to description from articles collection. 

db.articles.update({title:'web design'} ,{$rename:{'description':'details'}})

11. Add additional tag in a specific document.

db.articles.update({'title':'learn node'}, {$push:{'tags':'node', 'html'}})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

  db.articles.update({'title':'learn node'}, {$set:{'tags':'node', 'html'}})
  db.articles.update({'title':'learn node'}, {'tags':'node'}})

13. Increment an auhtor's age by 5.  

db.articles.update({'title':'learn code'}, {$inc:{'author.age':5}})

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

db.articles.remove({"_id" : ObjectId("5e16d2443bef106a66807f3b")})

Use sample.js data for below queries.

1. Find all males who play cricket.

db.users.find({"sports":"cricket"} && {'gender':'Male'})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

db.users.update({'name':"Steve Ortega"}, {$push:{'sports':"golf"}})

3. Find all users who play either 'football' or 'cricket'.

db.users.find({"sports":'football'} || {"sports":"cricket"})

4. Find all users whose name includes 'ri' in their name.

db.users.find({'name':/ri/i})