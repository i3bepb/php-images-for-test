# Images php for run test

Dockerfiles for create images on php for run test. Images based on php:cli-alpine and contains **xdebug**, **composer**.

# Build base image

## php 7.2.34
1. Build from root directory
```shell
docker build -f php7234/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-7.2.34-cli-alpine3.12 ./php7234
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-7.2.34-cli-alpine3.12 sh
```

## php 7.3.33
1. Build from root directory
```shell
docker build -f php7333/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-7.3.33-cli-alpine3.15 ./php7333
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-7.3.33-cli-alpine3.15 sh
```

## php 7.4.33
1. Build from root directory
```shell
docker build -f php7433/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-7.4.33-cli-alpine3.16 ./php7433
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-7.4.33-cli-alpine3.16 sh
```

## php 8.0.30
1. Build from root directory
```shell
docker build -f php8030/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-8.0.30-cli-alpine3.16 ./php8030
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-8.0.30-cli-alpine3.16 sh
```

## php 8.1.32
1. Build from root directory
```shell
docker build -f php8132/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-8.1.32-cli-alpine3.21 ./php8132
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-8.1.32-cli-alpine3.21 sh
```

## php 8.2.28
1. Build from root directory
```shell
docker build -f php8228/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-8.2.28-cli-alpine3.21 ./php8228
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-8.2.28-cli-alpine3.21 sh
```

## php 8.3.19
1. Build from root directory
```shell
docker build -f php8319/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-8.3.19-cli-alpine3.21 ./php8319
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-8.3.19-cli-alpine3.21 sh
```

## php 8.4.5
1. Build from root directory
```shell
docker build -f php8405/Dockerfile.base -t i3bepb/php-for-test:1.2.6-php-8.4.5-cli-alpine3.21 ./php8405
```
2. So you can run, check
```shell
docker run --rm -it i3bepb/php-for-test:1.2.6-php-8.4.5-cli-alpine3.21 sh
```

# How use on local
The file **Dockerfile.dev** can be used to run tests. Build a local image to map local user to user inside the container. For example user (1000:1000). Run from root directory.
```shell
docker build -f Dockerfile.dev -t php74-for-test:1.0.0 --build-arg MYAPP_IMAGE=i3bepb/php-for-test:1.2.6-php-7.4.33-cli-alpine3.16 --build-arg LOCAL_USER_ID_ARG=1000 --build-arg LOCAL_GROUP_ID_ARG=1000 ./php7433
```
Run container in interactive mode for tests
```shell
docker run -it --rm -v $(pwd):/home/www-data/application php74-for-test:1.0.0 sh
```
Inside container run
```shell
php vendor/bin/phpunit
```
or
```shell
php vendor/bin/testbench package:test
```
or
```shell
php vendor/bin/testbench package:test --coverage
```
etc.