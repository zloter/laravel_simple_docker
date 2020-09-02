#Docker for Laravel 
docker-compose for laravel backend API

First, copy `.env.dist` to `.env` and set configuration to desired values

For default configuration .env of laravel app should look like that:
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=db_name
DB_USERNAME=db_user
DB_PASSWORD=db_password
```

Then we can start docker:
```
docker-compose up
```

I usually use this command in the normal mode as real-time logs are useful.
However, if you want to run this code in the detached mode simply use `-d` option.

You can also retrieve host to add it to /etc/hosts list or just use IP:
```
docker network inspect bridge | grep Gateway | grep -o -E '[0-9\.]+'
```

Then we can connect to php container and install application normally:
```
docker-compose exec php bash
```

Heavily influenced by https://github.com/carlosas/docker-for-symfony