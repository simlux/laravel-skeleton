<p align="center"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

# Laravel Skeleton
## Setup a new project
```
git clone git@github.com:simlux/laravel-skeleton.git path/to/project
```

```
composer install
```

```
php artisan key:generate
php artisan app:name AppName
```

## Included Packages
* [Laravel Debugbar](https://github.com/barryvdh/laravel-debugbar) - barryvdh/laravel-debugbar
* [Laravel IDE Helper](https://github.com/barryvdh/laravel-ide-helper) - barryvdh/laravel-ide-helper
* [Laravel OPcache](https://github.com/appstract/laravel-opcache) - appstract/laravel-opcache
* [Laravel Generators](https://github.com/simlux/laravel-generators) - simlux/laravel-generators
* [Laravel Migration Helper](https://github.com/simlux/laravel-migration-helper) - simlux/laravel-migration-helper
* [Laravel Model UUID](https://github.com/simlux/laravel-model-uuid) - simlux/laravel-model-uuid

## Recommended Packages
* [Laravel Horizon](https://github.com/simlux/horizon) - laravel/horizon

    ```
    composer require laravel/horizon
    php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"
    ```
* [Curl](https://github.com/simlux/curl) - simlux/curl

    ```
    composer require simlux/curl
    ```
* [StringBuffer](https://github.com/simlux/string-buffer) - simlux/string-buffer

    ```
    composer require simlux/string-buffer
    ```
## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](http://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell at taylor@laravel.com. All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
