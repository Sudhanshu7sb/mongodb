1. Create a database named `blog`.
   Ans: use blog

2. Create a collection called 'articles'.
   Ans: db.createCollections('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields
   Ans : db.articles.insert({title:'mongo',author:"SSB"})

4) Find all the articles using `db.COLLECTION_NAME.find()`
   Ans: db.blog.find()

5) Find a document using \_id field.
   Ans: db.articles.find(ObjectId("5f2696e4581e2bdda2559558"))
6) Find documents using title and author's name field.
   Ans: db.articles.find({title:'mongo'})
   db.articles.find({author:'SSB'})

7) Find document using a specific tag.

8) Update title of a document using its \_id field.

Ans: db.articles.update({\_id:ObjectId("5f2696e4581e2bdda2559558")}, {\$set : {title:"MongoDB"}})

9. Update a author's name using article's title.

Ans: db.articles.update({title:"MongoDB"}, {\$set : {author:"sudhanshu"}})

10. rename details field to description from articles collection.

Ans : db.articles.update({title:"MongoDB"}, {\$rename : {details:"description"}})

11. Add additional tag in a specific document.

Ans: db.articles.update({title:"MongoDB"}, {\$set : {tag:"mongo database"}})

12. Update an article's tags using $set and without $set.

ANs: db.articles.update({title:"MongoDB"}, {\$set : {tag:"mongo database"}})

db.articles.update({title:"MongoDB"}, {tag:"mongo database using mongo shell without \$set"})

- Write the differences here ?

Ans: \$set : returns newer fields with older intact

      wihtout \$set : It replaces old document and only \_id and gender field is present in newer document.

13. Increment an auhtor's age by 5.
    Ans: db.articles.update({"tag" : "mongo database using mongo shell without $set"}, {$inc : {age:5}})

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.

ANs: db.articles.remove({\_id : ObjectId("5f26ab5fb95b350d810cbee4")})

Use sample.js data for below queries.

1. Find all males who play cricket.

ANs: db.mongorepoblog.find({gender: "Male",sports:"cricket"})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

Ans: db.mongorepoblog.find({name:"Steve Ortega"},{\$set : {sports:golf}})

3. Find all users who play either 'football' or 'cricket'.

Ans: db.mongorepoblog.find({\$or: [{sports:"cricket"},{sports:"football"}]})

4. Find all users whose name includes 'ri' in their name.
   Ans: db.mongorepoblog.find({name:/ri/i})
