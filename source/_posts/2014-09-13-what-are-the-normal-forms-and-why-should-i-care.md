---
title   : "Database Normalization: What Are the Normal Forms and Why Should I Care?"
layout  : post
excerpt : <p>As web developers, we're required to be familiar with technologies across the whole stack. With our hands in so many domains, it can be hard to gain expertise in many of them. This is often the case when it comes to database theory &mdash; a subject which isn't shiny, popular or new. That's where I found myself, so I set out to dig a bit deeper. And here's what I learned.</p>
---

As web developers, we're required to be familiar with technologies across the whole stack. Front-end languages, back-end languages, various frameworks and libraries, server administration, and &mdash; of course &mdash; databases. With our hands in so many domains, it can be hard to gain expertise in many of them. Our attention devoted to keeping up with the cutting edge. For the not-so-cutting-edge, we sometimes just learn what we have to.

This is often the case when it comes to database theory &mdash; a subject which isn't shiny, popular or new. Developers without a Computer Science degree simply learn the basics of relational databases and some general rules for indexing...and move on.

That's where I found myself, so I set out to dig a bit deeper. And here's what I learned. Join me on this short blog tour of the basics of *database normalization*. You'll learn some history, some new vocabulary and look at the first three Normal Forms. If you want your database decisions to have foundational substance behind them, read on.

### E.F. Codd and the Relational Database Model

Edgar Frank Codd was an Englishman born in 1923. He studied mathematics and chemistry at Oxford and served as a pilot in World War II. After the war, he moved to New York to work for IBM as a programmer. In the 60's he earned a doctorate in computer science. It was after earning his PhD that he published theories that would become the foundation of modern relational databases.

Codd published a model for relational databases and a number of requirements for a database to be truly "relational". These are called "normal forms". The term "database normalization" refers to the process of making your database "normal" &mdash; making it fit the requirements to be relational.

### Why Normalize Your Database?

One of the top goals of database normalization is to eliminate redundant data. When I say redundant data, I mean data that repeats itself. Redundant data is problematic, because when it comes out of sync the database suddenly contains untrue data. (This is called a "modification anomaly".) Who wants a database full of lies?

Various sources cite a number of further benefits:

1. Normalized databases generally require less redesign whenever extending the structure.
1. Normalized databases are generally more informative to users.
1. Normalized databases avoid bias toward a particular pattern of querying.

### Why Not Normalize Your Database?

Like all things in the realm of technology, database normalization is a trade-off. The more you normalize your database, the more complex your queries tend to become. Why? Because there are two goals at odds here: making the relationships "pure", and making it easy to get the data you want in the desired format. The "purer" the relationships, the more resources tend to be necessary to get the data you need.

So I'm just going to come out and say it: You don't always want a completely normalized database. There's a balancing act between your app's performance (queries with less joins, aggregations, etc.) and your database's sanity.

### First Normal Form (1NF)

### Second Normal Form (2NF)

### Third Normal Form (3NF)

### Recap

"The key, the whole key, and nothing but the key"

Vocabulary definitions

### References

http://www.bkent.net/Doc/simple5.htm
http://www.dcs.warwick.ac.uk/~hugh/TTM/The-Relational-Model.pdf
http://researcher.watson.ibm.com/researcher/files/us-fagin/tods77.pdf
