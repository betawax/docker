# Docker Stack

Docker LEMP stack for local PHP development.

✔︎ Get up and running with Docker Compose in minutes  
✔︎ Hassle free setup of local development environments  
✔︎ Pre-configured services for included LEMP containers

**Stack**

🚀 PHP 🚀 MySQL 🚀 Nginx 🚀 Node

**Also Included**

🚀 Composer 🚀 NPM 🚀 OpenSSL

## Usage

1. Place `docker-compose.yml` and `docker/` into your project directory
2. See the `.env.example` for a list of supported environment variables
3. Get Docker up and running

```
docker-compose up -d
```

Now you can access your local development environment either via `http://localhost` or `https://localhost` in your browser. By default, Nginx points to `public` as the document root.

For SSL, see [this](https://stackoverflow.com/a/31900210/1620163) on how to enable self signed certificates in Chrome.

## Running commands in services

Use `docker-compose exec <service> <command>` as usual:

```
docker-compose exec php composer install
docker-compose exec node npm install
```

Or to get an interactive prompt:

```
docker-compose exec php /bin/bash
```

## License

Licensed under the MIT license.
