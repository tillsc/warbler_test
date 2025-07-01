# warbler_test

A minimal Rails 8 application to reproduce WAR deployment issues under JRuby 10 using [Warbler](https://github.com/jruby/warbler).

## Purpose

This app serves as a reproduction case for issues encountered when generating and deploying `.war` files from a JRuby-based Rails 8 application using Warbler (latest `main` branch). See related issue:

> https://github.com/jruby/warbler/issues/560

## Environment

- **Ruby**: JRuby 10.0.0.1 (Ruby 3.4.2)
- **Java**: OpenJDK 24.0.1
- **Rails**: 8.0.2
- **Tomcat**: 9.0.x (tested with 9.0.106)
- **OS**: macOS (Apple Silicon)

## Gems

The key dependencies used:

- [`rails`](https://rubygems.org/gems/rails): ~> 8.0.2
- [`activerecord-jdbcsqlite3-adapter`](https://github.com/jruby/activerecord-jdbc-adapter): for JRuby and SQLite
- [`warbler`](https://github.com/jruby/warbler) (from GitHub master)
- `puma` for local development
- `jbuilder` and `web-console` for convenience

## Usage

To build the `.war` file:

```bash
rails war
```

This invokes Warbler via its Rake task and generates warbler_test.war in the project root. You can then deploy it to a servlet container like Tomcat.

## Notes

* This app uses no custom config/warble.rb.
* The database is SQLite via JDBC (only activerecord-jdbcsqlite3-adapter is used on JRuby).
* No additional features or routes are defined—this is a minimal Rails welcome page app.
* Deployment to Tomcat currently fails due to a missing class error (org.jruby.CompatVersion) under JRuby 10, likely caused by outdated assumptions in jruby-rack or Warbler internals.