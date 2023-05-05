# Docker PHPStan

Simple docker images containing installed version of phpstan to run phpstan commands without the need to install it. Supports different PHP Versions and has extra packages installed compared to the offical package

### Example Commands:

- PHP 8.2:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.2 stan analyse```

- PHP 8.1:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.1 stan analyse```

- PHP 8.0:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.0 stan analyse```