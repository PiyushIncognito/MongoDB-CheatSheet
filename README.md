# MongoDB-CheatSheet

# MONGODB

- Non-Relational Database
- Use Dynamic Schemas
- MongoDB can be used in supporting content management systems, online and offline gaming applications, e-commerce systems, mobile applications, data analytics section, archiving, as well as logging.
- Used by Adobe, LinkedIn, FourSquare, MetLife, eBay, SAP

## Mongo

**“mongo”** is a command-line shell that connects to a specific instance of **“mongod”**

In simple words mongo is a program or it issues commands to **mongod**

---

## Mongod

“mongod” is the “Mongo Daemon” its basically the host process for the database

In simple words to take action on commands given by mongo or like a compiler

---

## Difference between SQL and MongoDB

| SQL | MongoDB |
| --- | --- |
| 1) In SQL we says Tables | 1) In Mongodb we says Collection |
| 2) Relational DB | 2)Non-Relational DB |
| 3) rows | 3) documents (BSON) |
| 4) columns | 4) fields |

```jsx
{
    'name': 'Harry',                         field: value
    'lang': 'JavaScript',                    field: value
    'member_since': 5                        field: value
 }
```

---

## **1. Database Commands**

### **View all databases**

```
show dbs
```

### **Create a new or switch databases**

```
use dbName
```

### **View current Database**

```
db
```

### **Delete Database**

```
db.dropDatabase()
```

## **2. Collection Commands**

### **Show Collections**

```
show collections
```

### **Create a collection named 'comments'**

```
db.createCollection('comments')
```

### **Drop a collection named 'comments'**

```
db.comments.drop()
```

## **3. Row(Document) Commands**

### **Show all Rows in a Collection**

```
db.comments.find()
```

### **Show all Rows in a Collection (Prettified)**

```
db.comments.find().pretty()
```

### **Find the first row matching the object**

```
db.comments.findOne({name: 'Harry'})
```

### **Insert One Row**

```
db.comments.insert({
    'name': 'Harry',
    'lang': 'JavaScript',
    'member_since': 5
 })
```

### **Insert many Rows**

```
db.comments.insertMany([{
    'name': 'Harry',
    'lang': 'JavaScript',
    'member_since': 5
    },
    {'name': 'Rohan',
    'lang': 'Python',
    'member_since': 3
    },
    {'name': 'Lovish',
    'lang': 'Java',
    'member_since': 4
}])
```

### **Search in a MongoDb Database**

```
db.comments.find({lang:'Python'})
```

### **Limit the number of rows in output**

```
db.comments.find().limit(2)
```

### **Count the number of rows in the output**

```
db.comments.find().count()
```

### **Update a row**

```
db.comments.update({name: 'Shubham'},
{'name': 'Harry',
    'lang': 'JavaScript',
    'member_since': 51
}, {upsert: true})
```

### **Mongodb Increment Operator**

```
db.comments.update({name: 'Rohan'},
{$inc:{
    member_since: 2
}})
```

### **Mongodb Rename Operator**

```
db.comments.update({name: 'Rohan'},
{$rename:{
    member_since: 'member'
}})
```

### **Delete Row**

```
db.comments.remove({name: 'Harry'})
```

### **Less than/Greater than/ Less than or Eq/Greater than or Eq**
```
db.comments.find({member_since: {$lt: 90}})
```

```
db.comments.find({member_since: {$lte: 90}})
```

```
db.comments.find({member_since: {$gt: 90}})
```

```
db.comments.find({member_since: {$gte: 90}})
```
