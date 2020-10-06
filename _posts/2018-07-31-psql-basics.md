---
layout: post
title:  "The basics of using the psql terminal"
date:   2018-07-31
categories: development
---

Psql is the terminal for working with Postgres. You'll use it to query the databases.

> *Think before you type or press return!* It's easier to do something than it is to undo! I personally always use transactions when altering data!

## Connect to a database

The following command shows how you can connect to a database. You'll be prompted for your password, of course.

```
[user@server ~]$ psql -h <host> -U <username> -d <database>
```

## The psql prompt

Once you're logged into a database, you'll see the psql prompt.

```
[user@server ~]$ psql -h 127.0.0.1 -U robert -d test_database
psql (9.2.10, server 9.2.9)
Type "help" for help.

test_database=#
```

## Common Commands

### List databases

`\l` (or `\list`)
`\l+` (or `\list+`)

Lists the names, owners, character set encodings, and access privileges of all the databases in the server. If + is appended to the command name, database sizes, default tablespaces, and descriptions are also displayed. (Size information is only available for databases that the current user can connect to.)

```
test_database=# \list
```

### Switch database

`\connect` (or `\c`)

Allows you to connect to a different database that lives on the same server as the one you're currently connected to.

```
test_database=# \connect test_database2
You are now connected to database "test_database2" as user "robert".
test_database2=#
```

### Timing

By default the timing (timing in milliseconds) of query results will not be available, but you can turn it on by using the following command:

```
test_database=# \timing
Timing is on.
test_database=#
```

### List columns

If you want to know what columns are available in a particular table, you can describe the table by using `\d table_name`. You can also run the `\d` command on its own to display information on all tables in the database.

```
test_database=# \d orders
	  Table "public.orders"
   Column   |  Type   | Modifiers
------------+---------+-----------
 id         | integer | not null
 cust_id    | integer | not null
```

### Exit the terminal

To quit from the psql terminal type `\q`

```
test_database=# \q
[user@server ~]$
```

### Write a query

Use nano (or whatever editor you like) to edit your query:

```
test_database=# \e
```

Or

```
test_database=# SELECT * FROM orders\e
```

This opens your default text editor inside the psql terminal. As you can see from the examples above, you can start the editor before or after typing the query.

> *Configure the editor in your .bash_profile* otherwise it'll open in an editor like vim which could be difficult if you're not used to it. See below

```
export PSQL_EDITOR=nano
```

### Expanded display

By default, your results will be displayed across the screen in `less`. You can display the results vertically by using `\x` - expanded display.

```
test_database=# \x
Expanded display is on.
test_database=#
```

## The prompt

The default psql prompt, waiting for input will look like:

```
test_database=#
```

If you've typed a query and hit [return] without ending it with a semicolon, you'll see the prompt changes to:

```
test_database-#
```

The semicolon marks the end of a query, so pressing [return] without a terminating `;` suggests to psql that you would like to continue writing your query on a new line, for example:

```
test_database=# SELECT
test_database-# *
test_database-# FROM orders
test_database-# ;
```

Also a `#` indicates you have an open bracket/mismatched quote somewhere in your query and it will show quoting with `'#`, `"#` or `$#` prompts. For example:

```
test_database=# SELECT * FROM orders WHERE id IN (
test_database(# 1,2,3
test_database(# );
```

### Stopping a query or clearing the input

From time to time, you might want to stop a query you're running or you've started to type a query and want a fresh prompt. You can do this with `[ctrl]+[c]`:

```
test_database=# SELECT * FROM orders
test_database-# ^C
test_database=#
```

## Transactions

In some cases, you do not want an SQL statement to take effect unless another one completes or you get the output you're expecting. For example, when you want to delete some orders, you want to make sure you've only deleted the ones you've specified.

A transaction is a set of statements executed as a single unit. [See the PostgreSQL docs on transactions.](https://www.postgresql.org/docs/current/static/tutorial-transactions.html)

### Start a transaction

You'll start a transaction using `BEGIN` followed by a semi-colon:

```
test_database=# BEGIN;
BEGIN
test_database=#
```

### Make your changes

Here's an example of a query that didn't go to plan. The transaction should auto rollback even if you made a commit but to be sure, use the `ROLLBACK` command.

```
test_database=# BEGIN;
BEGIN
test_database=# DELETE FROM orders WHERE id = 20;
ERROR:  update or delete on table "orders" violates foreign key constraint "delivery_details_order_id_fkey" on table "delivery_details"
DETAIL:  Key (id)=(20) is still referenced from table "delivery_details".
test_database=# ROLLBACK;
ROLLBACK
test_database=#
```

### Check your results

After you've started a transaction and run your `UPDATE`, or `DELETE` (for example), you should check the results before committing the transaction. A simple select on your results should be enough and the output of the query will also help e.g. if you're expecting to update 100 records and it updates 200, you know you should rollback.

```
test_database=# BEGIN;
BEGIN
test_database=# SELECT id, name FROM orders WHERE id = 182;
 id  |        name
-----+---------------------
 182 | Robert Order
(1 row)

test_database=# DELETE FROM orders WHERE id = 182;
DELETE 1
test_database=# SELECT id, name FROM orders WHERE id = 182;
 id | name
----+------
(0 rows)

```

### Rollback

In case the result of one statement is not what you expected, you can use `ROLLBACK` to abort the current transaction and restore values to the original values.


```
test_database=# BEGIN;
BEGIN
test_database=# DELETE FROM orders WHERE id > 182;
DELETE 5000
test_database=# SELECT id, name FROM orders WHERE id = 182;
 id | name
----+------
(0 rows)

test_database=# ROLLBACK;
ROLLBACK
```

### Commit

When you call `COMMIT`, all the previous statements are committed together as a single unit.

```
test_database=# BEGIN;
BEGIN
test_database=# SELECT id, name FROM orders WHERE id = 182;
 id  |        name
-----+---------------------
 182 | Robert Order
(1 row)

test_database=# DELETE FROM orders WHERE id = 182;
DELETE 1
test_database=# SELECT id, name FROM orders WHERE id = 182;
 id | name
----+------
(0 rows)

test_database=# COMMIT;
COMMIT
```
