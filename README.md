#Docker for Laravel 
docker-compose for laravel backend API

First, copy `.env.dist` to `.env` and set configuration to desired values

For default configuration .env of laravel app should look like that:
```
DB_CONNECTION=mysql
DB_HOST=db_name
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=db_user
DB_PASSWORD=db_password
```

First we will build our containers:
```
docker-compose build
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



Heavily influenced by https://github.com/carlosas/docker-for-symfony