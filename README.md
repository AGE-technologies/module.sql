# Duct module.sql

A [Duct][] module that adds a SQL database connection pool and
[Ragtime][] migrations to a configuration.

[duct]:    https://github.com/duct-framework/duct
[ragtime]: https://github.com/weavejester/ragtime

## Installation

To install, add the following to your project `:dependencies`:

    [duct/module.sql "0.3.2"]

## Usage

To add this module to your configuration, add the `:duct.module/sql` key:

```edn
{:duct.module/sql {}}
```

By default the module looks for a database URL in the
`JDBC_DATABASE_URL` and `DATABASE_URL` environment variables, but you
can specify it directly by setting the `:database-url` key:

```edn
{:duct.module/sql {:database-url "jdbc:sqlite:db/example.sqlite"}}
```

To add migrations:

```edn
{:duct.migrator/ragtime {:migrations [#ig/ref :example.migration/create-foo]}}
```

See [migrator.ragtime][] for more information.

[migrator.ragtime]: https://github.com/duct-framework/migrator.ragtime

## License

Copyright © 2017 James Reeves

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
