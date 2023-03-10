# OS2forms med Forløb installation profile for Drupal 9

This is a Drupal 9 installation profile for OS2forms project.

<<<<<<< HEAD
### Create a new drupal project
```
composer create-project drupal/recommended-project os2forms
```

### Require this Drupal install profile.
```
composer require os2forms/os2forms_forloeb_profile
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
=======
## Create a new drupal 9 project with dev stability to allow all required packages to be installed.
```
composer create-project drupal/recommended-project:^9.0 os2forms
```

### !!!NOTE Temporary installation of install profile

--

@todo Update this section after release of composer cleanup.
- Remove added repositories
- Remove aliases
- Update require command.
- Remove "composer config minimum-stability dev"

--

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

2) Change composer config
```
composer config --no-plugins allow-plugins.zaporylie/composer-drupal-optimizations true
composer config --no-plugins allow-plugins.cweagans/composer-patches true
composer config --no-plugins allow-plugins.simplesamlphp/composer-module-installer true
composer config minimum-stability dev
```

3) Require the development version of os2forms_forloeb_profile and aliases of os2forms/os2forms_forloeb and os2forms/os2forms.
```
composer require "os2forms/os2forms:dev-composer_cleanup as 3.3.0" "os2forms/os2forms_forloeb:dev-composer_cleanup as 2.5.0" os2forms/os2forms_forloeb_profile:"dev-composer_cleanup" --with-all-dependencies
```

### Install the os2forms_forloeb_profile
See https://www.drush.org/latest/commands/site_install
>>>>>>> develop
