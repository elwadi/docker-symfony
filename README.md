### Docker multicontainer

Docker multi-container with [Symfony3](https://symfony.com) + [MySQL](https://mysql.com) + [PHP7-FPM](https://php.net) + [Nginx](https://www.nginx.com/)

### Starting

In order to make it work you need [Docker](https://docs.docker.com) & [Docker Compose](https://docs.docker.com/compose/)

Once you've your docker environment ready, clone this repo

```sh
git clone https://github.com/0x13a/docker-symfony && cd docker-symfony
```

### Configuration

Well, now you have to configure your MySQL server credentials, port & address here in the `docker-compose.yml`

```yml
db:
    image: mysql
    ports:
        - 127.0.0.1:3306:3306
    networks:
        - appnet
    volumes:
        - "./.data/db:/var/lib/mysql"
    environment:
        MYSQL_ROOT_PASSWORD: yourSecurePasswordHere
```

You have to configure your Symfony folder as well here in the `docker-compose.yml`

```yml
php:
    build: php7-fpm
    ports:
        - 127.0.0.1:9000:9000
    networks:
        - appnet
    links:
        - db:mysqldb
    volumes:
        - ../local-symfony-folder:/var/www/symfony
        - ./logs/local-symfony-folder:/var/www/symfony/app/logs
```

### Usage

Build your docker multicontainer

```sh
docker-compose build
```

Run your multicontainer

```sh
docker-compose up -d
```

Now your Symfony app is running at `http://localhost`

---

Learn more at [https://docs.docker.com/compose/](https://docs.docker.com)