### Docker multicontainer

Docker multi-container with [Symfony3](https://symfony.com) + [MySQL](https://mysql.com) + [PHP7-FPM](https://php.net) + [Nginx](https://www.nginx.com/)

![logo](https://github.com/0x13a/docker-symfony/blob/master/logo/docker-symfony.png)

### Starting

In order to make it work you need [Docker](https://docs.docker.com) & [Docker Compose](https://docs.docker.com/compose/)

Once you've your docker environment ready, clone this repo

```sh
git clone https://github.com/0x13a/docker-symfony && cd docker-symfony
```



### Configuration

Well, now you have to configure your **MySQL password** and **Symfony folder**, here in the `.env` conf file

```sh
MYSQL_ROOT_PASSWORD=root
SYMFONY_APP_VOLUME=./local-symfony-folder 
```


### Usage

Build and run your docker multicontainer

```sh
docker-compose up -d
```

Now your Symfony app is running at `http://localhost`

---

Learn more at [https://docs.docker.com/compose/](https://docs.docker.com)
