# OS2Forms Forløb profile Change Log
All notable changes to this project should be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

See ["how do I make a good changelog record?"](https://keepachangelog.com/en/1.0.0/#how)
before starting to add changes.

## [Unreleased]

- Adding cache_control_override as a soft dependency (composer only)
- Installing cache_control_override module on hook_install
-
## [1.13.0] - 25.09.2023

- Fixed missing icons on administration menu
- Removed dependency to config_entity_revisions

## [1.12.0] - 13.06.2023

### Removed
 - modules/os2forms_permissions_by_term moved to os2forms/os2forms repo
 - modules/os2forms_webform_list moved to os2forms/os2forms repo

## [1.11.0] - 10.03.2023
- Added github action for checking changelog changes when creating pull requests
- Updated readme
- Removed webform_embed from repositories
- Removed array keys from repositories list
- Updated drupal core dependency
- Updated gin dependency
- Updated os2forms dependency
- Updated os2forms_forloeb dependency
- Added cweagans/composer-patches as dependency
- Removed drupal/dynamic_entity_reference (It belongs in os2forms/os2forms_forloeb)
- Changed composer patching configuration

## [1.10.0]

### Added
 - Feature/user permissions
 - Feature/user management

## [1.9.0]

### Added
- Github CI action for checking Drupal Coding standards with PHP Code Sniffer


## Example of change log record
```
## [x.x.x] Release name
### Added
- Description on added functionality.

### Changed/Updated
- Description on changed/updated functionality.

### Deprecated
- Description of soon-to-be removed features.

### Removed
- Description of removed features.

### Fixed
- Decription of bug fixes.

### Security
- Security in case of vulnerabilities.

```
