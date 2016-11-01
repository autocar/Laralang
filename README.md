# Laralang's documentation

[![StyleCI](https://styleci.io/repos/69460815/shield?branch=master)](https://styleci.io/repos/69460815)
![License](https://img.shields.io/github/license/24aitor/laralang.svg?style=flat-square)

## Getting Started

### Step 1. Require it with composer

```
composer require aitor24/laralang
```

### Step 2. Register service provider

Add the next line to config/app.php inside `'providers' => [` :

```
Aitor24\Laralang\LaralangServiceProvider::class,
```

### Step 3. Add Laralang Alias

Add the next line to config/app.php inside `'aliases' => [` :


```
'Laralang'   => Aitor24\Laralang\Facades\Laralang::class,
```



## Examples

### Traslations

You shold call it like:

```php

{!! Laralang::trans('<your string>', '<from_locale>', '<to_locale>') !!} <!-- structure -->


{!! Laralang::trans('Hello world', 'en', 'es') !!} <!-- it should prints: Hola mundo -->

```

Moreover, you can call it without define <from_locale> nor <to_locale>, and it would setup default values of `config/laralang.php`.

```php

{!! Laralang::trans('hello world') !!}

```

#### Debugging translations

Debug option let you to know the reason of an unexpected result.

When you download our project, debug default value is true but you can modify in `config/laralang.php`. Furthermore you can modify it in a specific translation like next example.

```php

{!! Laralang::trans('hello world')->setDebug(true) !!}

```


### 'base' translations

```php
@lang('laralang::base.welcome')

{{trans('laralang::base.welcome')}}

{{trans('laralang::base.welcome_to', ['app_name' => 'Your app name'])}}

{{trans_choice('laralang::base.users_mp', 1)}}

{{trans_choice('laralang::base.users_mp', 5)}}
```
