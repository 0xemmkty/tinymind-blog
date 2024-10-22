---
title: System Design Note
date: 2024-10-22T02:39:29.132Z
---

https://learning-guide.gitbook.io/system-design-interview/chapter-01-scale-from-zero-to-millions-of-users
### 10.21
Designing a system to support millions of users is challenging and requires continuous improvement. In this chapter, a system for a single user is built and gradually scaled to serve millions. By the end, you will learn techniques to tackle system design interview questions.

## Single Server Setup
Every complex system starts simple. Initially, all components (web application, database, cache, etc.) run on a single server. The request flow begins when users access the website through a domain name, and DNS returns the IP address. Afterward, an HTTP request is sent to the web server, which responds with HTML or JSON.

## Traffic Sources
Web Application: Uses server-side languages (e.g., Java, Python) for logic and client-side languages (e.g., HTML, JavaScript) for rendering.
Mobile Application: Communicates with the web server via HTTP, often using JSON for API responses.
##Scaling with Databases
As the user base grows, the single server is split into multiple servers—one for handling traffic (web layer) and another for the database (data layer). This separation allows independent scaling.

## Database Choices
Relational databases are also known as Relational Database Management Systems (RDBMS) or SQL databases. Some of the most popular ones include MySQL, Oracle Database, PostgreSQL, etc. Relational databases use tables and rows to represent and store data. You can use SQL to perform join operations between different database tables.

Non-relational databases are also known as NoSQL databases. Some popular ones include CouchDB, Neo4j, Cassandra, HBase, and Amazon DynamoDB. These databases are categorized into four types: key-value stores, graph stores, column stores, and document stores. Non-relational databases typically do not support join operations.
Relational databases are usually the default choice, but NoSQL may be preferable when low latency, unstructured data, or high-volume storage is needed.  
Your application requires ultra-low latency.

Your data is unstructured, or you don’t have any relational data.

You only need to serialize and deserialize data (JSON, XML, YAML, etc.).

You need to store large volumes of data.

## Vertical vs Horizontal Scaling
Vertical Scaling: Increasing a single server’s resources (CPU, RAM) is simple but has limits and no redundancy.
## Horizontal Scaling: Adding more servers to a resource pool is better for large applications.
For high traffic, horizontal scaling is more suitable, and load balancing becomes essential to distribute traffic across servers, preventing downtime and slow responses.