# OS2forms med Forløb installation profile for Drupal 8

This is a Drupal 8 installation profile for OS2forms project.

## Create a new drupal 9 project
```
composer create-project drupal/recommended-project:^9.0 os2forms
```

### !!!NOTE Temporary installation of install profile
@todo Update this after release of composer cleanup.

1) Add our development sources to repositories list.
```
"repositories": [
...
    {
        "type": "vcs",
        "url": "https://github.com/itk-dev/os2forms_forloeb_profile"
    },
    {
        "type": "vcs",
        "url": "https://github.com/itk-dev/os2forms_forloeb"
    },
    {
        "type": "vcs",
        "url": "https://github.com/itk-dev/os2forms"
    }
],
```

2) Use aliases to build project on our development sources.
```
"require": {
...
    "os2forms/os2forms": "dev-composer_cleanup as 3.3.0",
    "os2forms/os2forms_forloeb": "dev-composer_cleanup as 2.5.0",
},
```

3) Require the development version of os2forms_forloeb_profile.
```
composer require os2forms/os2forms_forloeb_profile:"dev-composer_cleanup" --with-all-dependencies
```

### Setup your local settings file

web/sites/default/settings.local.php
```
/**
 * Database connection.
 */
$databases['default']['default'] = [
  'database' => '',
  'username' => '',
  'password' => '',
  'host' => '',
  'port' => '',
  'driver' => '',
  'prefix' => '',
];

/**
 * Config directory.
 */
$settings['config_sync_directory'] = '../config/sync';

/**
 * Hash salt.
 */
$settings['hash_salt'] = '';
```

### Setup settings.php
```
cp web/sites/default/default.settings.php web/sites/default/settings.php
```

Add local settings reference to web/sites/default/settings.php
```
if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
   include $app_root . '/' . $site_path . '/settings.local.php';
}
```

### Require drush for your project
```
composer require drush/drush
```

### Install site with this installation profile
```
vendor/bin/drush -y site-install os2forms_forloeb_profile
```

## Usage
It's not supposed to use this profile outside https://github.com/os2forms/os2forms8 project.