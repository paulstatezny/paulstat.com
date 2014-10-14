---
title   : "Database Normalization: What Are the Normal Forms and Why Should I Care?"
layout  : post
excerpt : <p>As web developers, we're required to be familiar with technologies across the whole stack. With our hands in so many domains, it can be hard to gain expertise in many of them. This is often the case when it comes to database theory &mdash; a subject which isn't shiny, popular or new. That's where I found myself, so I set out to dig a bit deeper. And here's what I learned.</p>
---

Web developers are required to know technologies all across the stack. With our hands in so many domains, we sometimes only learn what's necessary to get the job done. We know that our product will be better with a more thorough understanding, but it's hard to be an expert in so many areas.

When it comes to database theory, the Normal Forms are a great place to start. In this blog we'll cover some vocabulary and look at the first three Normal Forms.

#### "Normal Forms", eh?

Edgar Frank Codd was a pretty awesome dude. He went to college at Oxford, served as a pilot in World War II, and basically invented relational databases. No big deal.

In the 70's Codd outlined a number of rules a database must follow in order to be truly "relational". These he called the "normal forms". The term "database normalization" refers to the process of making your database follow these rules.

#### Why Normalize My Database?

Database normalization is all about structuring your tables the "right way". Keeping related data together, and keeping unrelated data (or not-closely-enough-related data) apart. In short, this is how the "pros" structure their data.

One of the primary goals of the Normal Forms is to eliminate redundant data. (Data that is repeated in multiple places.) When redundant data is updated in one place but not another, the database is suddenly "out of sync". It contains lies! Database theorists call this a "modification anomaly".

But also:

1. Normalized databases are generally more informative to users.
1. Normalized databases avoid bias toward a particular pattern of querying.
1. Normalized databases generally require less redesign whenever extending the structure.

#### Why Should I *Not* Normalize My Database?

Like many other areas of technology, database normalization involves a trade-off. When you normalize your database, you're often forcing yourself to write slightly more complex queries in order to get the data you want. But at the same time you gain all the benefits described above.

Why does normalization bring more complex queries with it? Because there are two goals that are at odds: the goal of making the relationships in the database "pure", and the goal of making it easy to retrieve the data you want in the format you want. The "purer" the relationships in your database, the more joins and aggregate functions are needed to get the data you want. (Examples to come; keep reading!)

So I'm just going to come out and say it: You don't always want a completely normalized database. You want to balance your app's performance with your database's sanity.

#### First Normal Form (1NF)

> "A relation is in first normal form if it has the property that none of its domains has elements which are themselves sets."
>
> E.F. Codd

First normal form is all about making each field in your database *atomic*. Atomic as in, "containing one atom of data."

Let's say you have a `people` table with a `phone_number` field. The table is not in 1NF if the phone number field contains multiple phone numbers:

`people`

| id | first_name | last_name | phone_number      |
|----|------------|-----------|-------------------|
| 1  |        joe | smith     |          555-1234 |
| 2  |      sally | jones     | 555-5678,555-8901 |
| 3  |       mary | johnson   | 555-4321          |

You can put the table in 1NF by making the data atomic, like so:

`people`:

| id | first_name | last_name |
|----|------------|-----------|
| 1  |        joe | smith     |
| 2  |      sally | jones     |
| 3  |       mary | johnson   |

`phone_numbers`:

| person_id | phone_number |
|-----------|--------------|
| 1         | 555-1234     |
| 2         | 555-5678     |
| 2         | 555-8901     |
| 3         | 555-4321     |

In real-world situations, 1NF is broken by fields with comma-separated values (`555-1234,555-5678`) and data serialized into JSON (`{numbers:["555-1234", "555-5678"]}`). As you can see, the solution is to extract that data out into its own table.

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
