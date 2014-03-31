# Theme Skeleton

> This is a skeleton for developing themes for your [Sorry](http://www.sorryapp.com) status page. It comes with simple example file structure, [Grunt](http://gruntjs.com/) tasks and various other useful utilities to get you up and running when developing your theme from scratch.
>
> **For more details on theme development, read our [Theme documenation](http://docs.sorryapp.com/themes)**.

## Getting The Theme

1. <a href="archive/master.zip">Download</a> the latest version
2. or clone the git repo: <code>git clone git@github.com:supporttime/theme-skeleton.git</code>

## Manual Deployment

The simplest option if you don't wish to make any changes to the theme is to upload the [zip file found in the dist folder](dist/theme.zip) through your user interface of your Sorry account.

**If you make any changes you'll need to rezip your theme before you upload it, [as per the Sorry docs](http://docs.sorryapp.com/themes/getting-started/uploading-your-theme.html).**

## Automatic Deployment with Grunt

To make development and deployment of your themes even easier you can use the included Grunt deployment tasks.

These tasks take the themes source code, bundle it into a deployable zip and upload it to your status page through the Sorry API.

### Install Grunt

From the command line, navigate to the root of this downloaded theme project and run `npm install`. npm will look at [package.json](package.json) and automatically install the necessary local dependencies listed there.

**Unfamiliar with `npm`? Don't have node installed?** That's a-okay. npm stands for [node packaged modules](http://npmjs.org/) and is a way to manage development dependencies through node.js. [Download and install node.js](http://nodejs.org/download/) before proceeding.

### Create the `sorry.json` File

We need somewhere to keep your Sorry login credentials. In the root of your project create a file called `sorry.json` which contains your username and password - don't worry, this will NOT be commited to your repo as we've included it in the `.gitignore`.

```json
{
  "username": "your email address goes here",
  "password": "your password goes here"
}
```

### Available Grunt commands

**Run all commands with the command line flag `--sorry-page="YOUR PAGE ID HERE"` to tell the tasks which page to deploy the theme too.**

You can find your page ID in the address bar of your Sorry account. i.e. a URL of `http://app.sorryapp.com/pages/my-page` means your page ID is `my-page`.

#### Deploy - `grunt deploy`

Bundles files in the `src` directory into `dist/theme.zip` before deploying it to your chosen page.

#### Watch - `grunt watch`

This is a convenience method for watching all the core HTML, CSS and JS assets in your theme, whenever you make a change to these files grunt will automaticly bundle and deploy your theme as above.

#### Release - `grunt release <:patch | :minor | :major>`

Bumps the [version number](#versioning) and creates a new git tag for the theme. You can append the release command with patch, minor or major depending on the version number increment you wish to make.

## Contributing

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

Once you are happy that your contribution is ready for production please send us a pull request, at which point we'll review the code and merge it in.

## Versioning

For transparency and insight into our release cycle, and for striving to maintain backward compatibility, This project will be maintained under the Semantic Versioning guidelines as much as possible.

Releases will be numbered with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and patch)
* New additions without breaking backward compatibility bumps the minor (and resets the patch)
* Bug fixes and misc changes bumps the patch

For more information on SemVer, please visit <http://semver.org/>.

## Authors & Contributors

**Robert Rawlins**

+ <http://twitter.com/sirrawlins>
+ <https://github.com/SirRawlins>

**Robin Geall**

+ <http://twitter.com/robingeall>

## Copyright

&copy; Copyright 2014 - See [LICENSE](LICENSE) for details.