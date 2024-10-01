### Installation commands only:

Before you going this steps, on your system should be installed: GIT  and  DOCKER COMPOSE

#### This command make in your system terminal:

```
git clone git@github.com:Wmag-team/docker_laravel_nginx_postgres_redis_localhost.git .
cd docker && docker-compose up -d --build && cd ..
docker exec -it laravel_app bash
```

#### Next commands in docker container command line:
```
composer create-project --prefer-dist laravel/laravel .
rm .env 
rm composer.json 
shopt -s dotglob
cp /var/snippets/* .
shopt -u dotglob

composer u

chmod -R 777 storage bootstrap/cache
php artisan migrate
php artisan optimize:clear
php artisan route:cache
php artisan route:clear
php artisan event:cache
php artisan event:clear
php artisan config:cache
php artisan config:clear
php artisan view:cache
php artisan view:clear

touch storage/logs/laravel.log
touch storage/logs/error.log
touch storage/logs/debug.log
sudo chmod -R 775 storage
sudo chmod -R ugo+rw storage

```
