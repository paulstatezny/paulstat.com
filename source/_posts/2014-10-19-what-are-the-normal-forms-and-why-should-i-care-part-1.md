---
title   : "Database Normalization: What Are the Normal Forms and Why Should I Care? (Part 1)"
layout  : post
excerpt : <p>Web developers are required to know technologies all across the stack. We know that our product will be better with a more thorough understanding, but it's hard to be an expert in so many areas. When it comes to database theory, the Normal Forms are a great place to start. In this two-part blog we'll cover some vocabulary and take a look at the first three Normal Forms.</p>
---

Web developers are required to know technologies all across the stack. With our hands in so many domains, we sometimes only learn what's necessary to get the job done. We know that our product will be better with a more thorough understanding, but it's hard to be an expert in so many areas.

When it comes to database theory, the Normal Forms are a great place to start. In this two-part blog we'll cover some vocabulary and take a look at the first three Normal Forms.

In part 1 we'll look at the normal forms as a whole and 1NF specifically.<br />
In part 2 we'll look at 2NF and 3NF.

#### "Normal Forms", eh?

The "Normal Forms" are rules a database must follow in order to be truly "relational". The term "database normalization" refers to the process of making your database follow these rules.

They were created in the early 1970's by a guy named E.F. Codd. (Who went to college at Oxford, served as a pilot in World War II, and then basically invented relational databases. No big deal.)

#### Why Normalize My Database?

Database normalization is all about structuring your tables the "right way". Keeping related data together, and keeping unrelated data (or not-closely-enough-related data) apart.

One of the primary goals of the Normal Forms is to eliminate redundant data. (Data that is repeated in multiple places.) When redundant data is updated in one place but not another, the database is suddenly "out of sync". It contains lies! Database theorists call this a "modification anomaly".

But also:

1. Normalized databases are generally more informative to users.
1. Normalized databases avoid bias toward a particular pattern of querying.
1. Normalized databases generally require less redesign whenever extending the structure.

#### Why Should I *Not* Normalize My Database?

Like many other areas of technology, database normalization involves a trade-off. When you normalize your database, you're often forcing yourself to write slightly more complex queries in order to get the data you want. But at the same time you gain all the benefits described above.

Why does normalization bring more complex queries with it? Because there are two goals in tension with each other: (1) making the relationships in the database "pure", and (2) making it easy to retrieve the data you want in the format you want. The "purer" the relationships in your database, the more joins and aggregate functions are needed to get the data you want. (Examples to come; keep reading!)

So I'm just going to come out and say it: You don't always want a completely normalized database. You want to balance your app's performance with your database's sanity.

#### First Normal Form (1NF)

> "A relation is in first normal form if it has the property that none of its domains has elements which are themselves sets."
>
> E.F. Codd<sup>[[1]](#ref1)</sup>

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

In real-world situations, 1NF is often broken in two ways. First, by fields with comma-separated values (`555-1234,555-5678`). Second, by data serialized into JSON (`{numbers:["555-1234", "555-5678"]}`). As you can see, the solution is to extract that data out into its own table.

##### When to Break 1NF

Like I said above, there are exceptions to the rule. Sometimes you just may want a field with serialized JSON or a comma-separated list. But first ask yourself a few questions:

 - Is this data going to be repeated elsewhere?
 - Am I going to be searching for an exact value in this column?
 - Do I need to perform transformations on the values in this column as part of a query?

If you answered yes to any of the above, you probably want to normalize the table to follow 1NF.

#### Part 2 Coming Soon!

Check back or [follow me on Twitter](https://twitter.com/paulstatezny) and I'll shoot out a tweet when part 2 of this blog goes live. The second and third normal forms add a lot of substance on top of 1NF.

#### References

<a name="ref1"></a>[1] Codd, E. F. "Further normalization of the database relational model". 1972.

[2] Kent, William. "[A Simple Guide to Five Normal Forms in Relational Database Theory](http://www.bkent.net/Doc/simple5.htm)". 1982.
