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

---------------------------------------------------------------------
## Transpiling

---------------------------------------------------------------------
## Bundling

---------------------------------------------------------------------
## Linting

---------------------------------------------------------------------
## Testing and Continuous Integration

---------------------------------------------------------------------
## HTTP Calls

---------------------------------------------------------------------
## Project Structure

---------------------------------------------------------------------
## Production Build

---------------------------------------------------------------------
## Production Deploy

