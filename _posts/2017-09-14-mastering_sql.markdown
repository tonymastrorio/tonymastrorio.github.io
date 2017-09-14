---
layout: post
title:  "Mastering SQL"
date:   2017-09-14 16:46:09 -0400
---


After being out of commission the past week due to Hurricane Irma, it's great to be back coding again!

When I began the Flatiron School curriculum, I had some basic knowledge of SQL and how it worked.

I've created basic apps using PHP and MySQL in the past that required the ability to insert, select and delete data from a database using SQL, but I knew there was a lot more to it, and am excited by how much I've learned recently.

Creating tables with SQL is as easy as:

```
CREATE TABLE dogs (
    id INTEGER PRIMARY KEY,
    name TEXT,
    age INTEGER,
    breed TEXT
);
```

It's important to note that every table you create should have an id column with a primary key that is an integer.  This integer will be auto-incremented so that each record in your database has a unique primary key.

And adding data to the table can be done like this:

```
INSERT INTO dogs (name, age, breed) VALUES ('Wrigley', 5, 'Labrador Retriever');
```

Notice that we are not passing in an ID, since the database takes care of assigning the ID for us automatically.

Suppose we wanted to get back all Labrador Retrievers in this table.  We would write the following SQL query:

```
SELECT * FROM dogs WHERE breed = "Labrador Retriever";
```

The * symbol tells our database to return all columns in the dogs table.

We can also use comparison operators to return specific data.  For example, if we want to see a list of all our puppies, we may write a SQL statement such as:

```
SELECT * FROM dogs WHERE age <= 2;
```

If you want to change data that has already been saved to your database, you can do so using an UPDATE statement, which would look something like this:

```
UPDATE dogs SET age = 6 WHERE name = "Wrigley";
```

This would change Wrigley's age to 6, following his next birthday.

At this point, the statements should start making logical sense.  So, if you want to DELETE a record from your table, you would do so like this:

```
DELETE FROM dogs WHERE id = 5 LIMIT 1;
```

This would delete the record with an id of 5 from the table.  For demonstration purposes, I added a LIMIT statement to the end to ensure only 1 dog is deleted (although this shouldn't be an issue in this case since our database ensures each record contains a unique ID).

After learning these basic statements, learning complex joins was a bit more challenging, but being able to join tables together and group and sort data from those tables is a great skill to have.  And while I know there are times that knowledge will come in very useful, it's also great to know that ActiveRecord abstracts a lot of repetetive SQL queries away for us.

In the next few weeks, I expect to have completed the Sinatra section and will have built my first app using the Sinatra framework.  Exciting times!


