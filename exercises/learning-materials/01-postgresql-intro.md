# PostgreSQL

Helpful hints/commands for `psql`:
- \h : list of all SQL commands available
- \? : list of all psql commands available
- \q : quit and exit psql
- be sure to end all SQL statements with a semi-colon

### Creating a Database with psql

First, let's get familiar some basic commands. Run the following command in your prompt: `username=# \l`

This will output a list of all of your PostgreSQL databases.

Let's create a new database and call it `testdb`. Run the following command:

```bash
CREATE DATABASE testdb;
```

Now that `testdb` has been created, running the `\l` command should output a list of databases with the newly created database `testdb` included.

### Connecting to a Database

In order to query a database, first you will need to connect to it. `testdb` will be the database that will be connected to for this example. Run the following command to connect to it:

```bash
\c testdb;
> You are now connected to database "testdb" as user "yourusername".
```


### Creating Tables

Now that there is a connection, tables can be created. It is as simple as writing raw SQL statements to create tables, insert rows, and to query.

For example, the following statement with create a table named `foods`:

```bash
CREATE TABLE foods (id INT, foodgroup TEXT, name TEXT);
```

To list all tables associated with the connected database run `\d`.

You can also list a specific table with `\d foods`.

Using `psql` is as simple as that! Now that you have the power to create tables, try inserting rows, updating columns, and querying data, all from the command line.

### Additional Resources

- [PostgreSQL Tutorial](https://www.tutorialspoint.com/postgresql/index.htm)
- [PostgreSQL Exercises](https://www.pgexercises.com/)
