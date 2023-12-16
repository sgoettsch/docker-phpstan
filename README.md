# Docker PHPStan

Docker images to run PHPStan commands without the need to install it.

Supports different PHP Versions and has extra PHP extensions installed compared to the official package.

The extra installed extensions should prevent undefined function or undefined class errors in the PHPStan run.

### Extra Extensions
- Sockets
- MySQLi
- XML
- Openswoole
- Redis

### Example Commands:

#### PHP 8.3:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.3 analyse /app```

#### PHP 8.2:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.2 analyse /app```

#### PHP 8.1:
```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.1 analyse /app```
