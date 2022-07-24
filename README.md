# Docker PHP Stack

A Docker stack for local PHP development.

## Stack

### Included Services

#### 🚀 PHP 8.0 or 7.4

- PHP-FPM 8.0 or 7.4 to choose from
- Common extensions and Composer pre-installed
- Support for both Laravel and WordPress CLIs

#### 🚀 Nginx or Apache

- Nginx or Apache to choose from
- Both services commonly pre-configured
- Self-signed SSL certificate included

#### 🚀 MySQL

- MySQL 8.0 with UTF-8 Unicode support
- Default database created on startup
- For MySQL 5.7 see this [tag](https://github.com/betawax/docker/tree/mysql-5.7)

#### 🚀 Node

- Node and NPM for frontend tasks

#### 🚀 Alpine

- Alpine Linux for fast build times

## Usage

### General Usage

1. Place `docker-compose.yml` and `docker/` into your project directory
2. Optionally, customize the provided container and service configuration
3. See the `.env.example` for a list of all supported environment variables

Lastly, get Docker up and running:

```
docker compose up -d
```

Now you can access your local development environment either via [http://localhost](http://localhost) or [https://localhost](https://localhost) on your host system. By default, the web service points to `public` as the document root. See the `.env.example` for how to connect to the database.

For SSL to work, you must [enable self-signed certificates](https://stackoverflow.com/a/31900210/1620163) in your browser.

### Customize the configuration

When customizing the provided configuration, you'll most likely want to:

- Pick a web service to use in `docker-compose.yml`
- Pick the PHP version to use in `docker/php/Dockerfile`
- Enable the Laravel or WordPress CLI in `docker/php/Dockerfile`
- Change the database environment variables in `docker-compose.yml`

### Run commands inside services

Use `docker compose exec <service> <command>`:

```
docker compose exec php composer install
docker compose exec node npm install
```

Or, to get an interactive prompt (shell):

```
docker compose exec web /bin/sh
```

### Use the Laravel or WordPress CLI

Enable and call the alias defined in `docker/php/Dockerfile`:

```
docker compose exec php artisan
docker compose exec php wp
```

## License

Licensed under the MIT license.
