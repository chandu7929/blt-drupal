# BLT Drupal
A Drupal 9 BLT-based project using the Acquia Drupal Recommended Project Template.

## Setup Local Environment.
BLT provides an automation layer for testing, building, and launching.
Drupal 9 applications. You can use local development tools such as Docker, Lando, Vagrant, etc.


## Prerequisites
- [Acquia Cloud Hooks](https://docs.acquia.com/blt/tech-architect/deploy/#cloud-hooks)
`blt recipes:cloud-hooks:init`
- [Acquia CI (Pipeline)](https://docs.acquia.com/cloud-platform/pipelines/yaml)
`blt recipes:ci:pipelines:init`
- [Configuration splits](https://docs.acquia.com/blt/developer/config-split/)
`blt recipes:config:init:splits`
- [Multisite Setup](https://docs.acquia.com/blt/tech-architect/multisite/)
`blt recipes:multisite:init`

### Local setup and development
1. Run the following command to install composer dependencies.
```
$ composer install
```
2. Generate local settings files.
```
$ blt blt:init:settings
```
3. Update the credentials for the local database in the `local.settings.php` file.
4. Then run the below command to set up the default site.
```
$ blt setup
```
In the case of multisite, use the `--site` param with the site name.
```
$ blt setup --site=[sitename]
```

### Continuous development
```
$ blt sync --site=[sitename]
```
