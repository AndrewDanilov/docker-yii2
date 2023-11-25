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

You need to run the following commands from the console of the yii_php container. To start bash within docker container, use the command:

```
docker exec -it yii_php bash
```

Run yii installation with container console:

```
composer create-project --prefer-dist yiisoft/yii2-app-advanced yii-project
```

Change current directory to project root:

```
cd yii-project
```

Initialize yii:

```
php init
```

Before using the database and migration, you need to configure the database configuration. In /common/config/main-local.php find this section:

```
'components' => [
    'db' => [
        'class' => \yii\db\Connection::class,
        'dsn' => 'mysql:host=yii_mysql;dbname=yii',
        'username' => 'yii',
        'password' => 'yii',
        'charset' => 'utf8',
    ],
```

Change `host` from `localhost` to `yii_mysql`, dbname, username and password set to `yii`, 

Then you can run migrations:

```
php yii migrate
```

Now you can open your app via:

http://localhost/ and http://admin.localhost/