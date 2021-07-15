# Ziggurat Profile Development Guide

If you want to maintain or actively work on the ziggurat profile you can follow
this guide to do so. We leverage the composer template to create a local
development environment.

# Getting a local environment prepared

Clone the ziggurat profile into a directory of your choosing. Make sure to have
the most current `2.x.x` branch checked out. Copy the path of the ziggurat
profile down, in a bash environment this can be done by running the command:
```bash
$ pwd
```
In a separate directory where you will be doing local development download this
template. This can be done using composer:
```bash
$ composer create-project ziggurat-distro/ziggurat-template ziggurat-local-dev --remove-vcs -s dev --no-install
```
`ziggurat-local-dev ` can be replaced with any name you desire.

Then in the `composer.json` you can replace the ziggurat repository with your local
version:
```json
        {
            "type": "path",
            "url": "/local/path/here"
        }
```
Also make sure to change the profile version requirement to `*` in `composer.json`
```
        "drupal/ziggurat": "*",
```

# Spinning up a local and installing

After preparing for development you can follow the `Local Development` step in
the [README][]

# Testing changes

You can test profile changes by requiring the profile within your local environment
you can use lando to do this:
```bash
lando composer require drupal/ziggurat
```

Sometimes changes to the profile require a full site re-install. The easiest way
to do this is by reinstalling lando. You can destroy your local environment
and re-install. __WARNING: this will remove all your local work such as configuration changes__

Destroy your local environment:
```bash
$ lando destroy -y
```

Then simply re-install following the `Local Development` step in
the [README][]

[README]: ../README.md
