## Laravel 8 Docker Starter

##### Build Docker

`docker-compose build`

##### Run Docker Containers

`docker-compose up -d`

##### Configuring Laravel

`DB_HOST=mysql` - This name comes from the MySQL service we created in the docker-compose.yml file, and is used in the Docker network to reference the service from other containers.

`APP_URL=http://localhost:8080` -  Add in the port number you’ve exposed in our nginx container to keep this pointing at a resolvable address.

##### Access MySQL Database

All you’re going to do is use `127.0.0.1` as the host, along with the port you’ve exposed under the MySQL service in our docker-compose.yml file (which for this example we’ve kept as the default 3308)

`Database: docker-laravel`
`Username: root`
`Database: 1234`

##### Running Commands

Laravel utilizes the command line fairly often for things like migrations, queues, and tests. Executing these on our Docker network is super easy using docker-compose’s exec command.

`docker-compose exec php php /var/www/artisan migrate`

reference: <https://dev.to/aschmelyun/the-beauty-of-docker-for-local-laravel-development-13c0>
