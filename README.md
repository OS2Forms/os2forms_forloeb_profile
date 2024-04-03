# OS2forms med Forløb installation profile for Drupal 9

This is a Drupal 9 installation profile for OS2forms project.

## Create a new drupal 9 project

Setting the stability to dev to allow all required packages to be installed and
also enable patching.

* Create a new drupal project.

```shell
composer create-project drupal/recommended-project:^9.0 os2forms
```

* Change composer config.

```shell
composer config --no-plugins allow-plugins.zaporylie/composer-drupal-optimizations true
composer config --no-plugins allow-plugins.cweagans/composer-patches true
composer config --no-plugins allow-plugins.simplesamlphp/composer-module-installer true
```

Set stability and ensure that patching is enabled. It will not automatically be
enabled by the `composer.json` files in the os2form profile.

```shell
composer config --json minimum-stability dev
composer config --json extra.enable-patching true
```

* Require the components of an os2forms project.

```shell
composer require "os2forms/os2forms:^3.3" "os2forms/os2forms_forloeb_profile:^1.11" --with-all-dependencies
```

### Install the os2forms_forloeb_profile

See https://www.drush.org/latest/commands/site_install
