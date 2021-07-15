
# Ziggurat Distribution Scaffold

The Ziggurat Distribution project template. Provides a Drupal 9 scaffold project
with the Ziggurat profile to kickstart development of a new instance of
a Ziggurat site.

## Dependencies

Composer, Lando, and Git are required to start and develop this project. The
project is containerized and wrapped with [Lando][].
* [Lando][]
* [Composer][]
* [git][]

## Getting started

Using composer make a copy of the project template using the following command
```bash
$ composer create-project ziggurat-distro/ziggurat-template PROJECT_NAME --remove-vcs -s dev --no-install
```
This will download the project template into a new directory, for your project it
is best to replace `PROJECT_NAME` with the name of your new project. This should
also match the name of the repository in git.

Then you should look to enable your new project's version control system, git
is the recommended one. Make sure you are in the project directory and use the
following commands to start and commit the initial version of your project:
```bash
$ git init
$ git add .
$ git commit
```
You should also look to set your remote repository and push this project there.

## Local Development

For local development [Lando][] is used. Before starting a sample site install
locally, make sure to set the project name in your `.lando.yml` file where it
says `PROJECT_NAME`. This name should match both the git and directory name of
the project.

From the project directory to get the initial packages and containers set up run:
```bash
$ lando start
```

Once lando has started and installed your dependencies you can now install the
profile. Make sure to replace `PROJECT_SITE_NAME` with the name of your new site:

```bash
$ lando drush site-install ziggurat --verbose --yes --site-mail=admin@localhost --account-mail=admin@localhost --site-name='PROJECT_SITE_NAME' --account-name=admin --account-pass=admin;
$ lando drush en -y ziggurat_default_content
$ lando drush en -y nodeaccess
```

The command above will  install Drupal with the ziggurat installation profile.
You can then log into Drupal as User 1 with `admin` / `admin` as the credentials.

## Contributing to the Ziggurat Profile

If you are interested in contributing to and testing the ziggurat profile you
can use this template, follow the guide found here: [Ziggurat Contributor][]

[Lando]: https://docs.devwithlando.io
[Composer]: https://getcomposer.org
[npm]: https://www.npmjs.com
[git]: https://git-scm.com/
[Ziggurat Contributor]: docs/ziggurat-profile-development.md
=======
