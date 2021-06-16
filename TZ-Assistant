# TZ Assistant
This package will help you to convert time for Users from UTC.
This package require to store user's desire timezone into your users table or the table used for auth.
## How to Install
Add below lines to your composer.json file.

```json
"repositories": [{
"type": "vcs",
"url": "https://github.com/usagar80/reward-engine"
}]
```
and then run composer reuire
```shell
composer require sup/tz-assistant
```
After that Publish Vendor files via

```shell
php artisan vendor:publish
```
and select service provider to publish.

After publishing you will see new migration script created.
In this file you can change table name from "users" to anything you want.
After completion run migration.

```shell
php artisan migrate
```
After migration you will see 2 colums.

1. Timezone
2. Timezone Format

In your app you have to create facility from where user can fill these
fields.

## How to use
To convert any UTC time to User's design time format 
you can do it by this way.
```php
// TO default format
Timezone::convertToLocal($post->created_at); // 16th Jun 2021 3:32:pm
// To specific format
Timezone::convertToLocal($post->created_at. 'd m Y'); // 16 6 2021
// With Timezone Name
Timezone::convertToLocal($post->created_at, 'Y-m-d g:i', true) // 2018-07-04 3:32 New York, America
```

### Using Blade Engine
```shell
@showUserDate($post->created_at)

// And with custom formatting
@displayDate($post->created_at, 'Y-m-d g:i', true)
// 2018-07-04 3:32 New York, America
```

## Saving the users input to the database in UTC
This will take a date/time, set it to the users timezone then return it as UTC in a Carbon instance.
```php
$post = Post::create([
'publish_at' => Timezone::convertFromLocal($request->get('publish_at')),
'description' => $request->input('description'),
]);
```

## Custom Configuration
Publishing the config file is optional.
After publishing Config file you can change default Datetime format.
