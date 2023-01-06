# OS2forms med Forløb installation profile for Drupal 9

This is a Drupal 9 installation profile for OS2forms project.

## Create a new drupal 9 project with dev stability to allow all required packages to be installed.
```
composer create-project --stability=dev drupal/recommended-project:^9.0 os2forms
```

### !!!NOTE Temporary installation of install profile

--

@todo Update this section after release of composer cleanup.
- Remove added repositories
- Remove aliases
- Update require command.

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
yes | composer require "os2forms/os2forms:dev-composer_cleanup as 3.3.0" "os2forms/os2forms_forloeb:dev-composer_cleanup as 2.5.0" os2forms/os2forms_forloeb_profile:"dev-composer_cleanup" --with-all-dependencies
```

### Install the os2forms_forloeb_profile
See https://www.drush.org/latest/commands/site_install