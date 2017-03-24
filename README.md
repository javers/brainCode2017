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
Having some snapshots saved in a JaversRepository, it's easy to browse objects' history 
and check how they looked like in the past. See [examples](http://javers.org/documentation/repository-examples/). 

So far, JaVers provides two implementations of JaversRepository:

* [SqlRepository](https://github.com/javers/javers/blob/master/javers-persistence-sql/src/main/java/org/javers/repository/sql/JaversSqlRepository.java),
* [MongoRepository](https://github.com/javers/javers/blob/master/javers-persistence-mongo/src/main/java/org/javers/repository/mongo/MongoRepository.java).
 
Our goal is to create the new implementation for DynamoDB.
 
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

See:
 
* [Introduction to DynamoDB Concepts](http://docs.aws.amazon.com/amazondynamodb/latest/gettingstartedguide/quick-intro.html)
* [Getting Started - Java](http://docs.aws.amazon.com/amazondynamodb/latest/gettingstartedguide/GettingStarted.Java.html)
* [Data Types](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes)
* [DynamoDB Documentation](https://aws.amazon.com/documentation/dynamodb/)

### JaVers development 

Checkout our github repository:

```
git clone https://github.com/javers/javers.git
cd javers
```

Checkout the `dynamoDb` branch:

```
git checkout dynamoDb
```

Build & test

```
./gradlew test

```

Run integration test for DynamoDB:

```
./gradlew javers-persistence-dynamodb:integrationTest
```

`DynamoDbSmokeTest` should be green and `DynamoRepositoryE2ETest` should be red since
`DynamoRepository` is not implemented yet.

## Your task

Your task is to make all tests green. 

* Fork the javers repository to dedicated space provided by BrainCode mentors.
* Implement `DynamoRepository`
* Work in a team? That's great, but don't push the whole team work at once. We want to see 
  individual commits of each team member.
* Create a pull request to `dynamoDb` branch in the javers repositorty.
* Make sure that CI is green, see [travis-ci.org](https://travis-ci.org/javers/javers/builds).
* Ask other attendee for the code review.

### How we evaluate your solution

* Code should be clean.
* End-to-end test is already there, but what about unit tests? Do we need them?
* Performance is the key. How you measure it?
  Provide performance tests and runtime statistics for various types of JaVers queries.
* Data model in DynamoDB should be well designed.
  Take a look how we designed database schemas for MongoDB and SQL.

## Required tools

* Java8
* Git
* DynamoDB Downloadable Version
  or DynamoDB Web Service (as a part of [AWS’s Free Tier](https://aws.amazon.com/free/)). 
* recommended IDE for Java: [IntelliJ IDEA](https://www.jetbrains.com/idea/) <br/>
* recommended GUI for DynamoDB: [Razor SQL](https://razorsql.com/)


