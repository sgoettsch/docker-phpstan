> [!WARNING]
> **This repository is archived and these images are deprecated.**
>
> They are no longer rebuilt, so they will not receive PHPStan, PHP or security updates.
> The images are still pullable, but you should migrate to the successors built in
> [sgoettsch/docker-service-container](https://github.com/sgoettsch/docker-service-container).

### Migration

| Deprecated image | Replacement |
| --- | --- |
| `ghcr.io/sgoettsch/docker-phpstan:latest-php8.1` | *none — see below* |
| `ghcr.io/sgoettsch/docker-phpstan:latest-php8.2` | `ghcr.io/sgoettsch/phpstan-8.2:latest` |
| `ghcr.io/sgoettsch/docker-phpstan:latest-php8.3` | `ghcr.io/sgoettsch/phpstan-8.3:latest` |
| `ghcr.io/sgoettsch/docker-phpstan:latest-php8.4` | `ghcr.io/sgoettsch/phpstan-8.4:latest` |

There is no PHP 8.1 successor image. Stay on a digest-pinned `latest-php8.1` reference, or move the
project to PHP 8.2 or newer.

If you use Renovate, add the replacement preset to your `renovate.json` and it will open the
migration PRs for you:

```json
{
  "extends": [
    "config:recommended",
    "github>sgoettsch/docker-service-container:replacements"
  ]
}
```

`github>sgoettsch/docker-phpstan` works as an alias for the same rules.

Image references inside `composer.json` scripts are not seen by any built-in Renovate manager. To
have those migrated too, additionally extend
`github>sgoettsch/docker-service-container:composerScriptImages`.

---

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

- PHP 8.4:
  ```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.4 analyse /app```

- PHP 8.3:
  ```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.3 analyse /app```

- PHP 8.2:
  ```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.2 analyse /app```

- PHP 8.1:
  ```docker run --rm --mount type=bind,src=$(pwd),target=/app ghcr.io/sgoettsch/docker-phpstan:latest-php8.1 analyse /app```
