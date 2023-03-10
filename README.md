# OS2forms med Forløb installation profile for Drupal 9

This is a Drupal 9 installation profile for OS2forms project.

## Create a new drupal 9 project with dev stability to allow all required packages to be installed.
```
composer create-project drupal/recommended-project:^9.0 os2forms
```

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
```

3) Require the components of an os2forms project.
```
composer require "os2forms/os2forms:^3.3" "os2forms/os2forms_forloeb:^2.5" "os2forms/os2forms_forloeb_profile:^1.11" --with-all-dependencies
```

### Install the os2forms_forloeb_profile
See https://www.drush.org/latest/commands/site_install
