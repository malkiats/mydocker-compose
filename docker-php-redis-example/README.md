# Docker with PHP and Redis example

While migrating from PHP 5.6 to PHP 7.1 we stumbled on a critical issue regarding our session management. Apparently PHP 7.1 triggers an error in the [redis extension](http://pecl.php.net/packages/redis) version 3.1.0.

```
Warning: session_start(): Failed to read session data: redis (path: tcp://localhost:6379)
```

## Solution

When downgrading the php extension for Redis to 3.0.0. the problem was resolved for PHP 7.1 (see #3b9b211). Unfortunately it's not resolved for PHP 7.0.

