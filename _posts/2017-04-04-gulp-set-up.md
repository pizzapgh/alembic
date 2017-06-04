---
title: Gulp Setup
category: General
excerpt: Thanks to a blogger by the name of Tania Rascia, I learned how use gulp to set up my web projects...
---

![alt text](/assets/gulp-logo.png "fart")

### Setting up gulp
Thanks to a kind blogger, I learned how to use gulp and set it up with my projects. Below are my notes. For a more in-depth explanation, visit [Tania Rascia's Site](https://www.taniarascia.com/getting-started-with-gulp//)

Gulp is a swiss army knife for web developers. It's a javascript task runner for project workflows utilizing helpful plugins such as sass and auto prefixers etc...

### Getting started

Download and install [Node.js](https://nodejs.org/en/)

Next, open PowerShell and run as Administrator

### First Step - Install gulp globally

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
npm install --global gulp-cli
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


### Second Step - cd into project directory and create package.jason file

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
npm init
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Third Step - install node and gulp

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
npm install --save-dev gulp
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Fourth Step - install gulp plugins

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
npm install --save-dev gulp-sass gulp-cssnano gulp-sourcemaps gulp-autoprefixer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Fifth Step

Create gulpfile.js in your project directory and add code below.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
'use strict';

var gulp = require('gulp');
var sass = require('gulp-sass');
var cssnano = require('gulp-cssnano');
var sourcemaps = require('gulp-sourcemaps');
var autoprefixer = require('gulp-autoprefixer');

gulp.task('workflow', function () {
	gulp.src('./src/sass/**/*.scss')
		.pipe(sourcemaps.init())
		.pipe(sass().on('error', sass.logError))
		.pipe(autoprefixer({
			browsers: ['last 2 versions'],
			cascade: false
		}))
		.pipe(cssnano())
		.pipe(sourcemaps.write('./'))

	.pipe(gulp.dest('./dist/css/'))
});

gulp.task('default', function () {
	gulp.watch('./src/sass/**/*.scss', ['workflow']);
});
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Seventh Step - create src folder and add your scss files

![alt text](/assets/gulp-dir.png "fart")

### Eighth Step - run gulp

~~~~~
gulp
~~~~~

After you run this command, go to your scss files, start editing them and save them. Go back to your directory and you'll notice a dist folder was created containing your minified css. Inside you'll notice the prefixes as well.
