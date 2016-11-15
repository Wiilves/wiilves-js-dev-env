# wiilves-js-dev-env

Starter Kit for Javascript Development Enviroment

Codifies lessons learned

---------------------------------------------------------------------
## Editors and Configuration

Maintain consistency with *.editorconfig*

Instal plugin for chosen editor from http://editorconfig.org/

VS Code Quick Open (Ctrl+P), paste the following command,
ext install EditorConfig 

---------------------------------------------------------------------
## Javascript Package Management

npm

run `npm install` to download packages specified in *package.json*

### Package Security
Security Scanning
Continuous Security monitoring for your node apps https://nodesecurity.io/

npm install -g nsp

nsp check

other options Bower,jspm.

---------------------------------------------------------------------
## Development Web Server

http-server, single command serves current directory.

live-server, support live-reloading.

express, highly configurable, Production grade, same on dev and prod.

koa, es 6 generators.

if webpack as bundler , built in, fast, serves from memory, hot reloading.

if Browserify as bundler, budo, hot reloading and integrates with Browserify.

Browsersync, 
  - dedicated IP for sharing work on LAN,
  - all interactions remain in sync (Great for cross-device Testing)
  - intgrates with Webpack, Browserify, Gulp.
  

  
### Sharing Work-in-progress

use localtunnel

npm install localtunnel -g

lt --port 3000

lt -- port 3000 --subdomain wiilves

---------------------------------------------------------------------
## Automation

Grunt
- configuration over code
- Writes intermediary files between steps
- Large plugin ecosystem

Gulp
- In-memory streams (pipes) ,fast.
- Code over confoguration
- Large plugin ecosystem

npm Scripts
- Declared in packages.json under 'scripts'
- Leverage your OS command line
- Directly use npm packages
- Call separete Node Scripts
- Convention-based pre/post hooks
- Leverage worlds largest package manager

- Use tools Directly
- No need for separate plugins
- Simpler debugging
- Easy to learn, simple.

---------------------------------------------------------------------
## Transpiling

TypeScript
- Superset of Javascript
- Typesafe
- Enhanced autocompletion
- Safer refactoring
- Clearer intent

Elm
- Complies down to JS
- Clean Syntax
- Immutable data structures
- Friendly errors
- All errors are compile-time errors


Babel
- Modern, standards-based JS, today. (import, const)
- Write standardized JS 
- Leverage full JS ecosystem
- Use experimental features earlier
- No type defs, annotations required
- ES6 imports are statically analyzable
- Test, Lint, Babel, Great libs, IDE = safety



- not npm specific
- Easier to read since isolated

.babelrc

or 

package.json
- One less file in your Project



---------------------------------------------------------------------
## Bundling

- CommonJS doesnt work in web browsers 
- Package projects into file(s) 
- Improve Node performance 

Module formats
- CommonJS    (var jquery = require('jquery')) 
- ES6 Module  (import jQuery from 'jquery')

Why use ES6 Modules ?

- Standardized 
- Statically analyzable (improved autocomplete, Intelligent refatoring, Fails fast, Tree shaking) 
- Easy to read (named imports, default exports) 



### Bundlers

- Browserify (Simple)
Bundle npm packages for the web 
Large plugin ecosystem for 

- Webpack (Comprehensive)
Bundles more than just JS 
Import CSS, images, etc like JS 
Built in hot-reloading web server 

- Rollup (Performance)
Treeshaking (eliminates code not used) 
Faster loading production code 
Quite new 
Great for library authors 
No hot reloading and code splitting yet 

- JSPM (Runtime loader, package manager )
Uses SystemJS, a universal module loader 
Can load modules at runtime 
built in package manager Can install from npm, git
Uses Rollup (Treeshaking)

Implement ES6 modules and bundling

Why Webpack ?
- Much more than just JS (CSS, images, fonts, HTML)
- Bundle splitting 
- Hot module reloading 

Set up webpack 

webpack.config.dev.js

How to debug transpiled and bundled code ?

Sourcemaps only Downloaded if you open developer tools 

`debugger`;

---------------------------------------------------------------------
## Linting

Why Lint ?

Enforce consistency 
- Curly brace positions 
- Trailing commas 
- Globals
- eval 

Avoid Mistakes 
- Extra parenthesis 
- Overwritting function 
- Assignment in conditional 
- Missing default case in switch 
- debugger / console.log 


Linting tools
- JSLint 
- JSHint 
- ESLint 

Use TSLint until ESLint adds support for TypeScript 


Configuration approaches for ESLint

Core decisions 
- Config format 
Dedicated config file (Not tied to npm) or package.json (One less file) 



- Which built-in rules 
http://eslint.org/docs/rules/


### Warnings or errors 
Warning 
- Can continue Development 
- Can be ignored 
- Team must agree: Fix warnings

 Error 
 - Breaks the build 
 - Cannot be ignored 
 - Team is forced to comply 

Which plugins, Enhance ESLint with plugins 

- eslint-plugin-react 
- eslint-plugin-angular 
- eslint-plugin-node 


present (airbnb)

Watching Files with ESlint 

eslint-loader, Re-lints files upon save 

eslint-watch

ESLint wrapper that adds file watch 
- not tied to webpack 
- Better warning/error formatting 
- Displays clean messages 
- Easily lint tests and build scripts too 

Linting experimental features 

ESLint directly 
- supports ES6 and ES7 natively and supports object spread 

Babel-eslint 
- Also lints stage 0-4 features 

Why Lint an automated Build Process ?
- One place to check 
- Universal Configuration 
- Part of continous intergration 

Set up ESLint 

`.eslintrc.json`


---------------------------------------------------------------------

## Testing and Continuous Integration


- Unit testing (single function or module)
- Integration testing (Interactions between modules)
- UI testing (Automate interactions with UI) 

6 Key Testing decisions 

### Testing framework 
- *Mocha (more configurable)
- Jasmine (built in Assertion Libraries )
- Tape (simple)
- Qunit (for testing jquery)
- AVA
- Jest (wrapper for Jasmine used by React)

### Assertion Libraries (Declare what you expect)
- *Chai 
- expect 
- Should.js 

### Helper Libraries 
- *JSDOM (run DOM-related tests without a browser) 
- Cheerio (Query virtual DOM using jQuery selectors)

### Where to run tests

Browser 
- Karma
- Testem

Headless Browser 
- PhantomJS 

In-memory DOM 
- JSDOM 

### Where to test files Belong

Centralized (folder called test)
- Less 'noise' in src folder 
- Deployment confusion
- Inertia 

*Alongside
- Easy imports 
- Clear visibility 
- Convenient to open 
- No recreating folder structure 
- Easy file moves (refactoring)


### When should tests run

Unit tests should run when you hit Save 
- rapid feedback 
- Facilitates TDD 
- Automatic = Low friction 
- Increases test visibilty 

Configure testing and write test

testSetup.js

---------------------------------------------------------------------

# Continuous Integration

Why CI ?
- Forgot to commit new file 
- Forgot to update package.json 
- Commit doesnt run cross-platform 
- Node version conflicts 
- Bad merge 
- Didnt run tests 

CI sever catches mistakes quickly 

What does a CI Server Do ?
- run automated build 
- run your tests 
- check code coverage 
- Automate deployment 

Choosing a CI server 
- Travis (linux)
- Appveyor (windows)
- Jenkins 

### Travis

.travis.yml

### Appveyor

appveyor.yml

---------------------------------------------------------------------

## HTTP Calls

Mocking HTTP calls

Mocking Approaches 
- node (http, request)
- browser (XMLHttpRequest, jQuery, Framework-based like Angular, Fetch)
- node and browser (Axios, SuperAgent, xhr)


Centralize API Calls 
- configure all calls 
- handle preloader logic (spinner)
- handle errors 
- Single seam for mocking 

Fetch with polyfil for cross browser.

Why Mock HTTP ?
- Unit Testing 
- Instant response 
- Keep working when services are down 
- Rapid prototyping 
- Avoid inter-team bottlenecks 
- Work offline 

How to Mock HTTP ?
- Static JSON 
- Create development webserver 
- api-mock 
- JSON server 
- JSON Schema faker (random data) 
- Browsersync 
- Express


1.Declare our Schema 
- JSON Schema faker 

Creating a Mock API Data Schema 
- mockDataSchema.js

2.Generate Random data 
- faker.js 
- chance.js 
- randexp.js 

Generating Mock data
- generateMockData.js

3.Serve Data via API 
- JSON Server (supports creat, updates, delets)

creates file api/db.json

---------------------------------------------------------------------

## Project Structure

Why include a demo App ?

Examples Helps
- Directory structure and file naming 
- Framework usage 
- Testing 
- Mock API 
- Automated deployment 

Codifies decisions

Project structure Tips

- JS belongs in a .js file 
- Consider organizing by Feature 
- Extract logic to POJOs 
1. pure logic 
2. no framework-specific code 

easy to test and reuse 

---------------------------------------------------------------------

## Production Build

### Minification
- remove comments 
- dead code elimination / Tree-shaking 
- debug via sourcemap 
- uglify 

`webpack.config.prod.js`

build.js

npm run build -s 

Sourcemaps 

Dynamic HTML
- htmlWebpackPlugin

### Bundle splitting 

Why ?
- Speed initial page load 
- Avoid re-downloading all libraries 

vendor.js

CommonsChunkPlugin

### Cache busting 
why ?
- Save HTTP Requests 
- force request for latest version 

1. Hash bundle filename 
2. Generate HTML dynamically 

WebpackMd5Hash

### Production Error logging 
- TrackJS 
- Sentry 
- New Relic

Error Metadata 
- browser 
- stack trace 
- previous actions 
- price 

Notifications & intgrations

Analytics and filtering 

### HTML Templates via EmbeddedJS (conditional logic to HTML)
http://www.embeddedjs.com/


---------------------------------------------------------------------
## Production Deploy

### Separating the UI from the API

why ?
1. Simple, low-risk, UI only deploys 
2. Separates concerns 
- Separate teams 
- Less to understand 
- Scale back-end separately 
3. Cheap UI hosting 
4. Serve UI via a content delivery network 
5. Use the API tech you like 

Hosting providers 
- AWS 
- Azure 
- Firebase 

Heroku for API 

baseUrl.js for API 

Surge for UI (https://surge.sh/) (Static web publishing for Front-End Developers)

- npm start       (development)
- npm run build   (production build)
- npm run deploy  (production deploy)

### Automated deployment 

### Handling starter kit updates 
- Yeoman 
- Github 
  1. fork starter kit for new projects 
  2. pull chnages from master 

- npm


### Inspiration 

Find your perfect React starter project
http://andrewhfarmer.com/starter-project/

react slingshote

Angular Seed projects
https://github.com/gianarb/awesome-angularjs

