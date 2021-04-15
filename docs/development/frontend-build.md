# Frontend Build

There is a frontend build system, which uses node to compile CSS and JS.

In day-to-day development, you do not need to worry about the build steps, as running development in docker
will automatically watch your SASS and JS files to recompile when there are changes.

If you want to run the project outside of docker, or you need to make changes to the build, read the getting started guide.

## Getting started

To run the frontend build manually, you will need [node](https://nodejs.org/en/) installed on your machine.

1. Go to the frontend directory: `cd frontend`
2. Install dependencies: `npm install`
3. Run the build command: `npm run build`

Available commands:

- `npm run build`: Build CSS and JS
- `npm run build:watch`: Build CSS and JS and then watch source files for changes
- `npm run lint:js`: Run linting on JS source code
- `npm run lint:css`: Run linting on SASS source code

## How it works

Build tasks are defined using [Gulp](https://gulpjs.com/) in `frontend/gulpfile.js`.

### CSS

SASS source files are compiled and minified into one CSS file.
The entrypoint SASS file is `frontend/css/main.scss` which compiles to `frontend/css/main.css`.

### JS

JavaScript files are compiled and minified into one JS file using [Webpack](https://webpack.js.org/) and [Babel](https://babeljs.io/) to transpile ES6 syntax into browser-friendly JavaScript.
The entrypoint JS file is `frontend/js/index.js` which compiles to `nhsuk/static/nhsuk/js/main.js`.

## Updating the NHS.UK frontend library version

We use the [NHS.UK frontend library](https://github.com/nhsuk/nhsuk-frontend) as our main source of CSS/JS and we should ensure that we are always using the latest version of the library. We use the NHS.UK frontend library using the npm package.

1. Go to the frontend directory: `cd frontend`
2. Update the NHS.UK frontend package: `npm install nhsuk-fronted@0.0.0` (replacing 0.0.0 with the [latest version of NHS.UK frontend](https://github.com/nhsuk/nhsuk-frontend/releases))
3. Run the build command: `npm run build`
4. Ensure you have checked the [NHS.UK frontend Change log](https://github.com/nhsuk/nhsuk-frontend/blob/master/CHANGELOG.md) and have made any changes required
