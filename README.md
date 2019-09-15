# WIP

# :currency_exchange: Laravel package for [currencylayer.com](https://currencylayer.com)

[![Latest Stable Version](https://poser.pugx.org/orkhanahmadov/laravel-currencylayer/v/stable)](https://packagist.org/packages/orkhanahmadov/laravel-currencylayer)
[![Latest Unstable Version](https://poser.pugx.org/orkhanahmadov/laravel-currencylayer/v/unstable)](https://packagist.org/packages/orkhanahmadov/laravel-currencylayer)
[![Total Downloads](https://img.shields.io/packagist/dt/orkhanahmadov/laravel-currencylayer)](https://packagist.org/packages/orkhanahmadov/laravel-currencylayer)
[![License](https://img.shields.io/github/license/orkhanahmadov/laravel-currencylayer.svg)](https://github.com/orkhanahmadov/laravel-currencylayer/blob/master/LICENSE.md)

[![Build Status](https://img.shields.io/travis/orkhanahmadov/laravel-currencylayer.svg)](https://travis-ci.org/orkhanahmadov/laravel-currencylayer)
[![Test Coverage](https://api.codeclimate.com/v1/badges/85b8405174a619e906e1/test_coverage)](https://codeclimate.com/github/orkhanahmadov/laravel-currencylayer/test_coverage)
[![Maintainability](https://api.codeclimate.com/v1/badges/85b8405174a619e906e1/maintainability)](https://codeclimate.com/github/orkhanahmadov/laravel-currencylayer/maintainability)
[![Quality Score](https://img.shields.io/scrutinizer/g/orkhanahmadov/laravel-currencylayer.svg)](https://scrutinizer-ci.com/g/orkhanahmadov/laravel-currencylayer)
[![StyleCI](https://github.styleci.io/repos/208126340/shield?branch=master)](https://github.styleci.io/repos/208126340)

Simple Laravel package for integrating with currencylayer.com currency rates.

## Installation

You can install the package via composer:

```bash
composer require orkhanahmadov/laravel-currencylayer
```

Publish package migration and config files:

```bash
php artisan vendor:publish --provider="Orkhanahmadov\LaravelCurrencylayer\LaravelCurrencylayerServiceProvider"
```

Set your currencylayer.com access key in `.env` file:

```bash
CURRENCYLAYER_ACCESS_KEY=your_key_here
```

You can find your access key in [Currencylayer dashboard](https://currencylayer.com/dashboard).

## Usage

You can type-hint `Orkhanahmadov\LaravelCurrencylayer\Currencylayer` to inject it from container:

```php
use Orkhanahmadov\LaravelCurrencylayer\Currencylayer;

class CurrencyController
{
    public function __construct(Currencylayer $currencyService)
    {
        $currencyService->live('USD', 'EUR');
    }
}
```

Anywhere outside container you can create instance of the service with `app()` method:

```php
$currencyService = app('currencylayer');
$currencyService->live('USD', 'EUR');
```

You can also use provided facade:
```php
\Currencylayer::live('USD', 'EUR');
```

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please email ahmadov90@gmail.com instead of using the issue tracker.

## Credits

- [Orkhan Ahmadov](https://github.com/orkhanahmadov)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
