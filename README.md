# TrackerTracker

Multi-project Scrum UI for [Pivotal Tracker](http://www.pivotaltracker.com).

![Screenshot](http://i.imgur.com/01xTYQx.png)

## Features

* Simultaneously view all projects current iteration and backlog
* Scrum-like UI
* Search across projects
* Filter down using any combination of labels, users, and searches
* All labels for all projects are displayed and have epic-like mini progress charts
* Columns can be rearranged
* Labels, column order, and selected projects survive browser restart
* Enter your Pivotal API token and user name and off you go
* Most actions are supported: update story descriptions, add notes, drag them to different columns to update their status
* It's pretty easy to write custom columns and filters

## Who Is This For?

Companies like [a particular technology startup](http://www.intentmedia.com/) that use Pivotal Tracker and have multiple small projects going at once, but no good way to visualize and track progress across them all.

## Project Status

This is beta software, use at your own risk. If you have any issues or feature requests, we would love to know, please [open an issue](http://github.com/intentmedia/TrackerTracker/issues). Contributions and pull requests are also very welcome.

## Installation

### Ubuntu Server Install

```sh
aptitude update
aptitude install build-essential redis-server git-core nodejs npm
npm -g install grunt
npm -g install forever
git clone git@github.com:intentmedia/TrackerTracker.git
cd TrackerTracker
npm install
grunt
cd app
forever start -l ~/forever.log -o ~/out.log -e ~/err.log app.js
```

### OS X Developer Install

1. Install **Homebrew**: [http://mxcl.github.com/homebrew/](http://mxcl.github.com/homebrew/)
2. Install **NodeJS**: [http://nodejs.org/](http://nodejs.org/)
3. Install **Redis**: `brew install redis`
4. Install **Grunt**: `npm -g install grunt`
5. Install **Testacular**: `npm -g install testacular`
6. Install **TrackerTracker**: `git clone git@github.com:intentmedia/TrackerTracker.git`
7. Install **NPM packages**: `cd TrackerTracker && npm install`

#### Running the app

```sh
cd TrackerTracker
grunt
cd app
node app
```

#### Running the Jasmine test suite manually

Assumes you have Chrome, Safari, and Firefox installed:

```sh
cd TrackerTracker/test
testacular run
```

#### Development

1. Have Testacular auto-run on file changes

```sh
cd TrackerTracker/test
testacular start
```

2. Have Grunt auto-run (jshint, concat, hogan compile) on file changes

```sh
cd TrackerTracker
grunt watch
```

## Browser Support

TrackerTracker is tested and built for Chrome, Safari, and Firefox stable. It seems fine in IE 9, but broken in IE 10. (Progress!) Fluid's localStorage implementation doesn't survive a restart, so for now Fluid should be considered unsupported.

