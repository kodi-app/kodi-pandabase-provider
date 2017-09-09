# PandaBaseProvider

ServiceProvider for KodiApp which provides Pandabase ORM.

## Installation

```bash
$ composer require kodi-app/kodi-pandabase-provider
```

## About PandaBase

Check the [official documentation](https://github.com/nagyatka/pandabase) (It supports PandaBase version v0.20.0 or above)

## Initialization of PandaBaseProvider

Initialization of one connection:
```php
$application->run([
    // ...
    KodiConf::SERVICES => [
        // List of Services
        [
            "class_name" => PandaBaseProvider::class,
            "parameters" => [
                "name"      =>  "test_connection",  // Connection's name.
                "driver"    =>  "mysql",            // Same as PDO parameter
                "dbname"    =>  "test_dbname",      // Same as PDO parameter
                "host"      =>  "127.0.0.1",        // Same as PDO parameter
                "user"      =>  "root",             // Same as PDO parameter
                "password"  =>  ""                  // Same as PDO parameter
                "attributes"=>  [
                    attributeName => value,
                    ...
                ]                                   // Optional, PDO attributes
            ]
        ]
        // ...
    ],
    // ...
]);
```

## Usage of Pandabase

```php

// You can get ConnectionManager via Application singleton instance
$db = Application::get("db");

// Or you can get it via ConnectionManager singleton instance
$db = ConnectionManager::getInstance();

```