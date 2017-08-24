basicMimifier
==============================
- [Installation](#installation)
- [After Proyect Installation](#after-proyect-installation)
  - [Run Project](#run-project)
  - [Build](#build)
- [Technology Stack](#technology-stack)
  - [NPM Dev dependencies](#npm-dev-dependencies)
----

Installation
------------
- Prerequisites (see _[Technology Stack](#technology-stack)_):
  * [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  * [NodeJS with npm](https://nodejs.org/en/)
    _(at the moment of this proyect is created the node and npm versions are : **NodeJs** LTS v6.11.2, **NPM** v3.10.10)_
  * [gulp](https://gulpjs.com/)
  * [Yarn](https://www.npmjs.com/package/yarn) also see [this article](https://scotch.io/tutorials/yarn-package-manager-an-improvement-over-npm)

- Installing Gulpjs as a global
  ```bash
  npm install gulp-cli -g
  ```
- Go to your proyect folders
    ```bash
    cd ~/ProyectsPath
    ```
- Getting Proyect from remote repository
  ```bash
  git clone git@github.com:pablojavierjimenez/basicMimifier.git
  ```
- After the proyect is downloaded, we go into the proyect folder
  ```bash
  cd basicMinifier
  ```
- And run Yarn Install
  ```bash
  yarn
  ```
----

After Proyect Installation
--------------------------
#### Run Project and Build
For Build the project you can run `gulp minify` or just `gulp`.
```bash
  $ node server.js

 APP running on localhost:3000
 API running on localhost:3000/api

```
---------------

```javascript
var gulp = require('gulp'),
    useref = require('gulp-useref'),
    gulpif = require('gulp-if'),
    uglify = require('gulp-uglify'),
    minifyCss = require('gulp-clean-css');

gulp.task('minify', function () {
    return gulp.src('app/*.html')
        .pipe(useref())
        .pipe(gulpif('*.js', uglify()))
        .pipe(gulpif('*.css', minifyCss()))
        .pipe(gulp.dest('dist'));
});

gulp.task('default',['minify']);
```
