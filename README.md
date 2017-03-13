# Brain Code 2017 &mdash; JaVers meets DynamoDB hackathon


Your goal is to write JaversRepository for [Amazon DynamoDB](https://aws.amazon.com/dynamodb/details/)

If you succeeded, your code will be merged to [JaVers](http://javers.org) master and released. <br/>
Thousands of JaVers users will be able to use DynamoDB with JaVers.
This could be your first open source contribution. Awesome!

## Intro

**Amazon DynamoDB** is a NoSQL database with a ColumnFamily data model, similar to Cassandra. 

**JaVers** is an open source Java library for domain objects auditing.
JaVers captures snapshots of domain objects (Entities) and persists them in a dedicated storage,
called JaversRepository.
Having some snapshots saved in a JaversRepository, it's easy to browse objects' history.
and check how they looked like in the past. See [examples](http://javers.org/documentation/repository-examples/). 

## Getting Started

### DynamoDB
Firts, try to [set up your DynamoDB](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SettingUp.html).
It's easier to start with DynamoDB running locally.

When you run it locally, launch Razor SQL and:
 
* type anything as AWS Access Key and AWS Secret Key
* set Max Results per Query to 1000

Create `hello_world` table with hash attribute `my_id`.

Run a few queries using unofficial,
SQL-like, [query language](http://razorsql.com/docs/dynamodb_sql_support.html) for DynamoDB, created by Razor.

Insert an item with `String` attribute:

```
insert into hello_world (my_id, my_text_col) values ('hello', 'world')
```

Insert another item with `Number` attribute:

```
insert into hello_world (my_id, my_int_col) values ('another', 5)
```

Select all items: 

```
select * from hello_world
```

As you can see, item attributes are added dynamically.

See [Introduction to DynamoDB Concepts](http://docs.aws.amazon.com/amazondynamodb/latest/gettingstartedguide/quick-intro.html)
<br/>
See [DynamoDB Documentation](https://aws.amazon.com/documentation/dynamodb/)

### JaVers

//TODO

## Required tools

* Java8
* Git
* DynamoDB Downloadable Version
  or DynamoDB Web Service (as a part of [AWS’s Free Tier](https://aws.amazon.com/free/)). 
* recommended IDE for Java: [IntelliJ IDEA](https://www.jetbrains.com/idea/) <br/>
* recommended GUI for DynamoDB: [Razor SQL](https://razorsql.com/)


