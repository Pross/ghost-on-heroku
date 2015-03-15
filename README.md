# [Ghost](https://github.com/TryGhost/Ghost) on [Heroku](http://heroku.com)

[![Build Status](https://travis-ci.org/Pross/ghost-on-heroku.svg?branch=master)](https://travis-ci.org/Pross/ghost-on-heroku)
[![GitHub issues](https://img.shields.io/github/issues/Pross/ghost-on-heroku.svg)](https://github.com/Pross/ghost-on-heroku/issues)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/Pross/ghost-on-heroku/master/LICENSE)
[![Donate Beer](https://img.shields.io/badge/Donate-Beer-brightgreen.svg)](https://www.changetip.com/tipme/Pross)

Ghost is a free, open, simple blogging platform. Visit the project's website at <http://ghost.org>, or read the docs on <http://support.ghost.org>.

## Deploying On Heroku

To get the latest version of Ghost running on Heroku, click the button below:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/cobyism/ghost-on-heroku)

Fill out the form, and you should be cooking with gas in a few seconds.

### Getting Started

- After deployment, visit the admin area at `YOURAPPNAME.herokuapp.com/ghost` to set up your blog.

- Your blog will be publicly accessible at `YOURAPPNAME.herokuapp.com`.

- Install the [Heroku Toolbelt](https://toolbelt.heroku.com/)

- Clone your app locally which will allow you to make changes and keep it up to date.

  ```sh
  heroku git:clone --app YOURAPPNAME
  ```
- Install the Heroku Repo plugin.

  ```sh
  heroku plugins:install https://github.com/heroku/heroku-repo.git
  ```

### Keeping Up To Date & Installing A Theme

Installing a theme is easy because we use bower to fetch the themes directly from github.

- Edit bower.json adding the theme to the array of dependencies.

- Commit your changes and push to Heroku, the new theme will be auto installed.

To update Ghost or any of the themes you added via bower you can tell Heroku to rebuild.

  ```sh
  heroku repo:rebuild -a YOURAPPNAME
  ```

### Note

**Image uploads are disabled** when deployed to Heroku, since Heroku app filesystems [aren’t meant for permanent storage](https://devcenter.heroku.com/articles/dynos#ephemeral-filesystem). If this is a problem for you, you should look into other ways to host your site.

### How this works

This repository is essentially a minimal web application that specifies [Ghost as a dependency](https://github.com/TryGhost/Ghost/wiki/Using-Ghost-as-an-NPM-module), and makes a deploy button available.

## Problems?

If you have problems using your instance of Ghost, you should check the [official documentation](http://support.ghost.org/) or open an issue on [the official issue tracker](https://github.com/TryGhost/Ghost/issues). If you discover an issue with the deployment process provided by *this repository*, then [open an issue here](https://github.com/cobyism/ghost-on-heroku).

## License

Released under the [MIT license](./LICENSE), just like the Ghost project itself.
