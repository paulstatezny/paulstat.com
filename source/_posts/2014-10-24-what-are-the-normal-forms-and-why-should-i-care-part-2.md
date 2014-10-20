---
title   : "Database Normalization: What Are the Normal Forms and Why Should I Care? (Part 2)"
layout  : post
excerpt : <p>Excerpt</p>
---

Introduction

#### Second Normal Form (2NF)

> "There can be no functional dependencies on a subset of a candidate key."

If that sentence is meaningless to you, that is to be expected. Let's remedy that by defining a few terms:

##### Functional dependency

> A field Y is "functionally dependent" on a field (or fields) X if it is invalid to have two records with the same X value but different Y values. That is, a given X value must always occur with the same Y value.
>
> [William Kent](http://www.iai.uni-bonn.de/III//lehre/vorlesungen/TDWA/WS07/1.pdf)

An example of a functional dependency: My first name (field Y) is functionally dependent upon my social security number. In other words: If a table contains my SSN and a first name associated with that SSN, that first name has to be Paul. In every instance. Make sense?

##### Candidate Key

> A Candidate Key can be any column or a combination of columns that can qualify as unique key in database. There can be multiple Candidate Keys in one table. Each Candidate Key can qualify as Primary Key.
>
> [SQL Authority](http://blog.sqlauthority.com/2009/10/22/sql-server-difference-between-candidate-keys-and-primary-key-2/)

##### Examples

Again, 2NF says that "there can be no functional dependencies on a subset of a candidate key." What's a subset? A subset is *part* of a key. So 2NF only applies to candidate keys that have more than 1 column. Yes, in case you didn't know, a key can have multiple columns.

Let's look at some examples. Here's a table that breaks 2NF:

#### Third Normal Form (3NF)

#### Recap

"The key, the whole key, and nothing but the key"

Vocabulary definitions

#### References

http://www.bkent.net/Doc/simple5.htm
http://www.dcs.warwick.ac.uk/~hugh/TTM/The-Relational-Model.pdf
http://researcher.watson.ibm.com/researcher/files/us-fagin/tods77.pdf
