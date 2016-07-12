# Introduction
A seed project for Angular 2 apps using Vaadin-polymer elements. Derived from mgechev/angular2-seed.
[![Angular 2 Style Guide](https://mgechev.github.io/angular2-style-guide/images/badge.svg)](https://angular.io/styleguide)
[![Build Status](https://travis-ci.org/mgechev/angular2-seed.svg?branch=master)](https://travis-ci.org/mgechev/angular2-seed)
[![Build Status](https://ci.appveyor.com/api/projects/status/github/mgechev/angular2-seed?svg=true)](https://ci.appveyor.com/project/mgechev/angular2-seed)
[![Join the chat at https://gitter.im/mgechev/angular2-seed](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mgechev/angular2-seed?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)
[![Dependency Status](https://david-dm.org/mgechev/angular2-seed.svg)](https://david-dm.org/mgechev/angular2-seed)
[![devDependency Status](https://david-dm.org/mgechev/angular2-seed/dev-status.svg)](https://david-dm.org/mgechev/angular2-seed#info=devDependencies)

Provides fast, reliable and extensible starter for the development of Angular 2 projects.

`angular2-seed` provides the following features:

- Allows you to painlessly update the seed tasks of your already existing project.
- Out of the box ServiceWorkers and AppCache support thanks to the integration with [angular/mobile-toolkit](https://github.com/angular/mobile-toolkit).
- Ready to go, statically typed build system using gulp for working with TypeScript.
- Production and development builds.
- Sample unit tests with Jasmine and Karma including code coverage via [istanbul](https://gotwarlost.github.io/istanbul/).
- End-to-end tests with Protractor.
- Development server with Livereload.
- Following the [best practices](https://angular.io/styleguide).
- Manager of your type definitions using [typings](https://github.com/typings/typings).
- Has autoprefixer and css-lint support.

# How to start

**Note** that this seed project requires node v4.x.x or higher and npm 2.14.7.

**Here is how to [speed-up the build on Windows](https://github.com/mgechev/angular2-seed/wiki/Speed-up-the-build-on-Windows)**.

In order to start the seed use:


```bash
git clone --depth 1 https://github.com/abhibly/Angular2-Seed-Project.git
cd angular2-seed
# install the project's dependencies
npm install
# install polymer dependencies by switching to client folder
bower install
# watches your files and uses livereload by default
npm start
# api document for the app
# npm run build.docs

# dev build
npm run build.dev
# prod build
npm run build.prod
```
# Changes done for integrating vaadin in seed-project
```bash
# Defined dependencies in project.config.ts
    this.SYSTEM_CONFIG_DEV.paths['@vaadin'] =
      `${this.APP_BASE}node_modules/@vaadin`;

    this.SYSTEM_BUILDER_CONFIG.packages['@vaadin/angular2-polymer'] = {
        main: 'index.js',
        defaultExtension : 'js'
    };
# imported vaadin elements in index.html
<script src="bower_components/webcomponentsjs/webcomponents-lite.min.js"></script>
<link rel="import" href="bower_components/vaadin-date-picker/vaadin-date-picker.html">

# imported polymer element in a component and defined the element name in directives list
import { PolymerElement } from '@vaadin/angular2-polymer';
 directives: [PolymerElement('vaadin-date-picker')]
 ```
 # Error recieved
 
 ```
Error: Error: XHR error (404 Not Found) loading http://localhost:5555/node_modules/@vaadin/package.json(…)
 
 ```
 # vaadin integration in angular2 tutuorial is found here https://vaadin.com/docs/-/part/elements/angular2-polymer/tutorial-index.html
# Code Derived from mgechev/angular2-seed. 
