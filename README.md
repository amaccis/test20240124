# Set-up

## containers building
```sh
docker-compose build
```

## app set-up
```sh
docker-compose run --rm cli symfony composer install
docker-compose run --rm cli symfony console doctrine:database:create
docker-compose run --rm cli symfony console doctrine:schema:create
```

## app start
```sh
docker-compose up -d
```

# Usage

Send requests (or browse) to
```
http://localhost/api
```