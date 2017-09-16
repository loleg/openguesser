OpenGuesser
===========

This is a web game about guessing and learning about geography through imagea and maps, made with Swisstopo's [GeoAdmin map of Switzerland](https://map.geo.admin.ch).

After several years of development as a series of GeoAdmin Storymaps - try the original [SwissGuesser game here](http://mf-swissguesser.prod.bgdi.ch/main/storymaps/storymap5/) - we play tested, forked and started a refresh of the project at [#GLAMhack 2017](http://make.opendata.ch/wiki/event:2017-09).

We updated all library dependencies but got rid of the old data loading mechanism, with the goal of connecting (later in real time) to open data sources such as Wikidata/Commons. 

A test is being done via the Wikidata Linked Data endpoint (see app/data/*.sparql), notably via datasets tagged 'glam' on Opendata.swiss for creating custom games.

There are a few other improvement ideas in mind already:

- Redesign the frontend to improve aesthetics and usability. 
- Add a new title and tutorial, complete with loading sequence.
- Difficulty levels.
- Multiple guesses.
- Cooperative play (e.g. ghost traces of a friend's guesses)
- High scores.
- Sound f/x!

..and we would be glad to see more ideas and any contributions: please raise an Issue or PR if you're so inclined!

# Authors

A number of people have worked on this project at some point. Please see contributors of the original project in [geoadmin/mf-swissguesser](https://github.com/geoadmin/mf-swissguesser/graphs/contributors)

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
