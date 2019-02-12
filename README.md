[![Latest Version](https://poser.pugx.org/wptrt/theme-sniffer/v/stable)](https://packagist.org/packages/wptrt/theme-sniffer)
[![Travis Build Status](https://travis-ci.org/WPTRT/theme-sniffer.svg?branch=master)](https://travis-ci.org/WPTRT/theme-sniffer)
[![Last Commit to Unstable](https://img.shields.io/github/last-commit/WPTRT/theme-sniffer/develop.svg)](https://github.com/WPTRT/theme-sniffer/commits/develop)

[![Minimum PHP Version](https://img.shields.io/packagist/php-v/wptrt/theme-sniffer.svg?maxAge=3600)](https://packagist.org/packages/wptrt/theme-sniffer)
[![Tested on PHP 5.3 to nightly](https://img.shields.io/badge/tested%20on-PHP%205.3%20|%205.4%20|%205.5%20|%205.6%20|%207.0%20|%207.1%20|%207.2%20|%20nightly-green.svg?maxAge=2419200)](https://travis-ci.org/WPTRT/theme-sniffer)
[![License: MIT](https://poser.pugx.org/wptrt/theme-sniffer/license)](https://github.com/WPTRT/theme-sniffer/blob/develop/LICENSE)
[![Number of Contributors](https://img.shields.io/github/contributors/WPTRT/theme-sniffer.svg?maxAge=3600)](https://github.com/WPTRT/theme-sniffer/graphs/contributors)


# Theme Sniffer

* [Description](#description)
* [Requirements](#requirements)
* [Installation](#installation)
* [Contributing](#contributing)
* [License](#license)

## Description

Theme Sniffer will help you analyze your theme code, ensuring the PHP and WordPress Coding Standards compatibility.

## Requirements

The Theme Sniffer requires:

* PHP 7.0 or higher.
* WordPress 4.7 or higher.

## Installation

### For themes development

* Download [zip file](https://github.com/WPTRT/theme-sniffer/releases/download/0.2.0/theme-sniffer.0.2.0.zip). [Note: Please use this distribution plugin zip. GitHub provided zip will not work.]
* Install this as you normally install a WordPress plugin
* Activate plugin

### For Theme Sniffer development

* Clone this repo under `wp-content/plugins/`
* Run `composer install`
* Run `npm install`
* Run `npm run build`
* Activate plugin

__Note__: If you build the plugin this way you'll have extra `node_modules/` and `vendor/` folders which are not required for the plugin to run, and just take up space. They are to be used for the development purposes mainly.

![Screenshot](screenshot.png?raw=true)

## Usage

* Go to `Theme Sniffer`
* Select theme from the dropdown
* Select options
* Click `GO`

### Options

* `Select Standard` - Select the standard with which you would like to sniff the theme.
* `Hide Warning` - Enable this to hide warnings.
* `Raw Output` - Enable this to display sniff report in plaintext format. Suitable to copy/paste report to trac ticket.
* `PHP version` - Select the minimum PHP Version to check if your theme will work with that version.

## Development

All of the development asset files are located in the `assets/dev/` folder. We have refactored the plugin to use the latest JavaScript development methods. This is why we are using [webpack](https://webpack.js.org/) to bundle our assets.

To start developing, first clone this repo under `wp-content/plugins/`. Then run in the terminal

`npm start`

This will run webpack in the watch mode, so your changes will be saved in the build folder on the fly. After you're done making changes, run

`npm run build`

This will create the `assets/build/` folder with js and css files that the plugin will use.

When developing JavaScript code keep in mind the separation of concerns principle - data access and business logic should be separate from the presentation. If you 'sniff' (no pun intended) through the js code, you'll see that `index.js` holds all event triggers and calls the method for sniff start that is located in the separate `ThemeSniffer` class. Business logic modules should contain plain JavaScript (no framework), which makes it reusable. Of course, there is still room for imporvement, so if you notice something that could be improved we incurage you to make a PR :)


