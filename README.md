Yii in Docker Template
======================

Template for quick start working with yii in docker container on local server.

Get this template
-----------------

```
git clone https://github.com/AndrewDanilov/docker-yii2.git docker-yii2
```

Start Docker Compose
--------------------

```
cd docker-yii2
docker compose up -d
```

Install Yii2
------------

Start bash within container:

```
docker exec -it php_yii bash
```

Run yii installation with container console:

```
composer create-project --prefer-dist yiisoft/yii2-app-advanced yii-project
```

Initialize yii:

```
cd yii-project
php init
```

Now you can open your app via:

http://localhost/ and http://admin.localhost/