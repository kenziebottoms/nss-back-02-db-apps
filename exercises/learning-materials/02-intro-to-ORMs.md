# ORMs

### Setup
First, install the CLI tool globally: `npm install -g sequelize-cli`

Then, let's escape all the pressure and stress of NSS by building some sandcastles on a sunny beach. Create a directory called `sequelize_sandcastles` and cd into it. Check this out:

```bash
mkdir sequelize_sandcastles && cd $_
```

Oooh, nifty. Learn something new every day, right?

Then `npm init` and install some dependencies:

```bash
npm install sequelize pg pg-hstore
```

Launch postgres, then using psql in a new terminal window/tab,
```bash
CREATE DATABASE sandcastledb;
```
HINT: don't forget the ";" at the end of the statement, and avoid capital letters.

Next, a quick `sequelize init` at the root of your project will create the basic folder/files you'll need. Your file structure should like something like this

```
├── config
│   └── config.json
├── migrations
├── models
│   └── index.js
├── package.json
└── seeders
```

Open up `config/config.json` in your editor. Here, you will see three configurations for three different environments: development, testing, and production. That's cool. Now you can mess around with building db in development mode, run tests against a whole other version in test mode, and keep a clean version, free from fake data and db-breaking experiments, when running in production.

Change `mysql` to `postgres`. For simplicity's sake, just worry about changing the default settings in `development` to match your project's info. You won't need to worry about `username` or `password`. Feel free to delete those.

```js
{
  "development": {
    "database": "sandcastledb", //the database you created with psql or in the PostgreSQL GUI
    "host": "127.0.0.1",
    "dialect": "postgres"
  },
  ...
}
```
Now you're ready to
+ Define the entities your db will store, as models
+ Configure the tables that will hold instances of those models by creating migration files
+ Seed the db with some placeholder data

### Resources
- [ORM Wikipedia page](https://en.wikipedia.org/wiki/Object-relational_mapping)
- [Sequelize](http://sequelize.readthedocs.io/en/1.7.0/)
- [Sequelize: Getting Started](http://docs.sequelizejs.com/manual/installation/getting-started.html)