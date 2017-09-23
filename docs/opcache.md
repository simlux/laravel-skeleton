# OPcache

## Resources
Medium.com: https://medium.com/appstract/make-your-laravel-app-fly-with-php-opcache-9948db2a5f93

## Settings
Enable OPcache
```
opcache.enable=1
```

How many Megabyte you want to assign to OPcache. Choose anything higher than 64.
```
opcache.memory_consumption=512
```

How many Megabyte you want to assign to interned strings. Choose anything higher than 16.
```
opcache.interned_strings_buffer=64
```

How many scripts can be cached. Make this as close as possible (or more) to the amount of scripts in your project. Choose any of these values: 3907, 7963, 16229, 32531, 65407, 130987.
```
opcache.max_accelerated_files=32531
```

This will revalidate the script. If you set this to 0(best performance), you need to manually clear the OPcache every time your PHP code changes (we will handle this in the next section). If you don’t want to clear it yourself, you can set this to 1 and configure the revalidate interval with opcache.revalidate_freq, this will cost you some performance as it needs to check for changes every x seconds.
```
opcache.validate_timestamps=0
```

This will preserve comments in your script, I recommend to keep this enabled, as some libraries depend on it, and I couldn’t find any benefits from disabling it (except from saving a few bytes RAM).
```
opcache.save_comments=1
```

Fast shutdown should give a faster mechanism for clearing memory.
```
opcache.fast_shutdown=0
```

So my final config looks like this:
```
opcache.enable=1
opcache.memory_consumption=512
opcache.interned_strings_buffer=64
opcache.max_accelerated_files=32531
opcache.validate_timestamps=0
opcache.save_comments=1
opcache.fast_shutdown=0
```

## Prepare your Laravel App
As mentioned earlier, we need to manually clear the OPcache every time we change PHP code. I created a handy package that gives you Artisan commands to work with OPcache.

To install follow the instructions in this repo: https://github.com/appstract/laravel-opcache

Next, add this command somewhere to the end of your deploy script (I put it just after artisan up) php artisan opcache:clear
The package also contains some other helpful tools for OPcache, you can read more about it on the Github page.

### Installation
Require via Composer:
```
composer require appstract/laravel-opcache
```

Add Service Provider in config/app.php
```
'providers' => [
    ...
    Appstract\Opcache\OpcacheServiceProvider::class,
    ...
];
```

### Usage
Login to your server/vm and run one of the commands.

Requests are only excepted from the same IP as the server IP.

Clear OPcache:
```
php artisan opcache:clear
```

Show OPcache config:
```
php artisan opcache:config
```

Show OPcache status:
```
php artisan opcache:status
```

Pre-compile your application code (experimental):
```
php artisan opcache:optimize
```

Programmatic usage:
```
use Appstract\Opcache\OpcacheFacade as OPcache;

OPcache::clear();
```