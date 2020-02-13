# NOTE

We will deploy laravel web app using docker container. We will deploy 3 container, the app container, web container, and db container.

### Get the latest Laravel

Get the code and enter that directory :

```
curl -L https://github.com/laravel/laravel/archive/v5.3.16.tar.gz | tar xz
cd laravel-5.3.16
```

### Install Dependencies

```
docker run --rm -v $(pwd):/app composer install
```

### clone this repo
```
git clone <git url>
```

### Run the laravel website
```
docker-compose up -d
```

### Test
Open localhost:8080 in your browser, and you will get HTTP response 500. It's happend because we should 
generate application key and run the optimize command, inside app container. Use this command :
```
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan optimize
```

Try open localhost:8080 again.


### I can learn this from
Medium : https://medium.com/@shakyShane/laravel-docker-part-1-setup-for-development-e3daaefaf3c
