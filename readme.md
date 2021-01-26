# CrudGenerator

Crud Generator automatically generates all necessary files for a complete crud. This includes factories, migrations, models, blades,
requests & seeders. This package also has the possibility to create relations between models.  

For relations to work you'll need to manually add comments to the User Model otherwise it won't generate it for you.  
These comments will be automatically added by models created by this CrudGenerator. Refer to Relations section for more info.

## Installation

Via Composer

``` bash
$ composer require flightsadmin/crudgenerator
```

## Usage
You'll need to publish the assets for the crud generator functionality to work.
``` bash
$ php artisan vendor:publish --provider="Flightsadmin\CrudGenerator\CrudGeneratorServiceProvider" --tag=assets
```

After this, head to `/crud` to see the crudgenerator and head to `/crud/relations` to
see the relations generator.  

If you would like to publish the other file such as config, stubs and views to customize them
you can do so with
```bash
$ php artisan vendor:publish --provider="Flightsadmin\CrudGenerator\CrudGeneratorServiceProvider"
```

### Relations
Models generated by this crudgenerator will include all required comments for relations to be made.  
Other models such as User by default will not have these comments which will not allow us to automate creating relations.  
If User will be one of you relations please add these comments to the model:

```php
protected $fillable = [
    'name', 'email', 'password',  // Fillables placeholder
];
```

And at the bottom of the Class itself (but still inside it):
```php
// Relation placeholder
```
