# L5-swagger ( Folksy adaptation )
This is a fork from [DarkaOnLine's L5-swagger](https://github.com/DarkaOnLine/L5-Swagger). The version is locked to version 8.1.0. 

For more information on how to use this package, please refer to the original fork.

### Changes
The main change from this package is the ability to define, from the "scanOptions" config key, after which processor we want to add our custom processor.

### Usage
For the base usage [please refer to the original documentation](https://github.com/DarkaOnLine/L5-Swagger/wiki).

As for the custom usage, we simpy added a config key `append-processors-after`, under `scanOptions` :
```php
// l5-swagger.php
return [
    'default' => 'default',
    'documentations' => [
       /* ... */
    ],
    'defaults' => [ 
        /* ... */
        'scanOptions' => [
            /* ... */
            'processors' => [
                // new \App\SwaggerProcessors\SchemaQueryParameter(),
            ],

            /**
             * Define after which Open Api's processors we want to happens the custom one.
             */
            'append-processors-after' => \OpenApi\Processors\BuildPaths::class,

            /* ... */
        ],
    /* ... */
];
```

The default value is `\OpenApi\Processors\BuildPaths::class`, which is the original value in the original fork.


