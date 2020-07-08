# SWCCGDB

This repository holds the source code of [SW:CCG DB](https://swccgdb.com).

# Looking for card data?

The data used by SW:CCG DB is at [PrestonStahley/swccgdb-json-data](https://github.com/PrestonStahley/swccgdb-json-data). If you want to fix a mistake in some card data, or add the data of a new card, you can [submit a pull request](https://github.com/PrestonStahley/swccgdb-json-data/pulls).

# Very quick guide on how to install a local copy

This guide assumes you know how to use the command-line and that your machine has php and mysql installed.

- install composer: https://getcomposer.org/download/
- clone the repo somewhere
- cd to it
- run `composer install` (at the end it will ask for the database configuration parameters)
- run `php bin/console doctrine:database:create`
- run `php bin/console doctrine:schema:create`
- run `php bin/console app:import:std ../thronesdb-json-data` or whatever the path to your ThronesDB JSON data repository is
- run `php bin/console app:import:trans ../thronesdb-json-data` if you want to import the translations
- run `php bin/console server:run`

## Setup an admin account

- register (or run `php bin/console fos:user:create <username>`)
- make sure your account is enabled (or run `php bin/console fos:user:activate <username>`)
- run `php bin/console fos:user:promote --super <username>`
