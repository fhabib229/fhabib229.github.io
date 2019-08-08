---
title: "SDC: Choosing a Database"
date: "2019-03-17"
path: "/sdc-choosing-db"
coverImage: "../images/sdc/images/sdc-choosing-db.jpg"
author: "Faris Habib"
excerpt: "Choosing a primary database for SDC"
tags: ["sdc", "system design capstone", "blogs"]
---

# Selecting a Primary Database

One important factor to keep in mind when reviewing the selection of the primary database is analyzing how the application functions **as it is, not as it functions in the real world.** In SDC we had to select one SQL DBMS and one NoSQL DBMS to work with. My team and I chose PostgreSQL as our SQL database and Apache Cassandra as our NoSQL database. Initial benchmarking of both databases were promising. I was able to insert 10 million records into the Postgres database in about 16 minutes and the same amount into Cassandra in 18 minutes using the same seeding technique for both: batch insertions.

  - PostgreSQL Development Seed Script Time
    ![benchmark records][one]

  - Cassandra Development Seed Script Time
    ![cassandra final benchmark][two]


When it came to select the primary database to deploy to AWS EC2 there were several key factors to consider:

  - Speed of data insertion
  - Preferred operation type for application (Read vs Write heavy application)
  - Size of deployment instance (T2 Micro)
  - Size of service and application

The ESPN application had 4 services to it:

  - Standings: Displays team statistics
  - Feed: Displays articles/blogs relating to the chosen NFL team to the page
  - Schedule: Displays the upcoming games the chosen team is expected to play
  - Team Leaders: Displays statistics of notable players of the chosen team.

Since speed was about the same for both databases I did not consider speed to be an important differentiating factor in choosing my primary database. Next, In each case these services successfully render the relevant information to the page from the database, but do not contain any additional functionality for users to add new data to the page themselves. This means that the only way the application is able to receive data is from inserting records in the back end. What this meant for our database choice is that we do not have a write-heavy application, rather we have a read-intensive application. Based on this factor PostgreSQL could be better suited to be our primary database. Another factor to consider is the constraint of our deployment instance, a T2 micro. While PostgreSQL is able to handle a T2 micro instance just fine Cassandra usually needs a larger instance (at least a T2 small) for deployment. This would be an additional cost to the project and would not meet the constraint place upon us, adding another compelling reason for PostgreSQL as our primary database. Another factor to consider is the overall size of the service and the application. The standings service takes about 5GB total of space with 10 million records, the other services take about the same size. This puts the total number of space for our application at about 30GB, which is suitable for a single node. Cassandra shines best when multiple nodes are needed for an application or applications, but because our application is reduce to a single node we would not be utilizing Cassandra to its potential.

In summary when considering size constraint of the deployment instance, primary application operation, and the size of the service and application overall it made sense to choose PostgreSQL as the primary database. With that being said, the question that one might ask is if we could have deployed our application with Cassandra, to which the answer would be yes, but not without sacrificing at least one of the constraint requirements for this project.

---

`youtube: watch?v=vnEO2DQInYU&feature=youtu.be`

---

[one]: ../images/sdc/images/benchmark1.png
[two]: ../images/sdc/images/cassandrabenchmark3.png