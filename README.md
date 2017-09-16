OpenGuesser
===========

This is a web game about guessing and learning about geography with Swisstopo's [GeoAdmin map of Switzerland](https://map.geo.admin.ch) and open data.

# Authors

The following people have worked on this project at some point:

- TBD
- ...

# Installation

The project is built with OpenLayers, jQuery and the Bootstrap framework, with a collection of tools powered by Node.js.

1. Install Node.js http://nodejs.org/download/
2. Install dependencies from the Node Package Manager (or Yarn, etc.) with this command at the project root:

`npm install`

This will install Grunt and Bower automatically. However, it is recommended that they are installed globally:

`npm install -g grunt-cli bower`

Run this command as root to use system-wide, or use the [nave.sh](https://github.com/isaacs/nave) utility for your local user.

Install dependencies

`bower install`

(or `node_modules/.bin/bower install`)

For generating documentation, the [Pygments](http://pygments.org/) utility is required, which can be installed as indicated [on the website](http://pygments.org/download/) or on Ubuntu/Debian systems as follows:

`# sudo apt-get install python-pygments`

## Preparing data

TBD

## Preparing translations

With a similar process, translations for this app are in a spreadsheet. Export to CSV and save the resulting file under `/app/data/i18n/translation.csv'. Then run:

`$ node util/translationCSV.js`

## Compiling resources

To a local server watching for changes, and open a browser:

`$ grunt server`

To create a `docs/` folder with HTML documentation, run:

`$ grunt docs`

See Grunt documentation and `Gruntfile.js` for other commands.

## Deploying releases

First you need to build the Bootstrap framework. From the `app/bower_components/bootstrap/` folder run:

`bootstrap$ npm install`

`bootstrap$ grunt dist`

Now you can build this project's distribution folder.

`$ grunt build`

Finally, zip up the `dist` folder and deploy it to the target host.

# Documentation

See [guesser](app/scripts/guesser.html) and [wms-custom-proj](app/scripts/wms-custom-proj.html) for a detailed code walkthrough.

For debugging the application, you can add `&debug=true` to the URL, which will include all images in the game instead of a random batch. The additional parameter `&ix=5` would then jump to the 5th image in the sequence.

# Licensing

The source code of this project is licensed under the [MIT License](LICENSE).
