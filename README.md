[![Code Climate](https://codeclimate.com/github/sloppylopez/apigee/badges/gpa.svg)](https://codeclimate.com/github/sloppylopez/apigee)
[![Travis](https://travis-ci.org/sloppylopez/apigee.svg)](https://travis-ci.org/sloppylopez/apigee)
[![Test Coverage](https://codeclimate.com/github/sloppylopez/apigee/badges/coverage.svg)](https://codeclimate.com/github/sloppylopez/apigee/coverage)
[![built with gulp](https://raw.github.com/cyparu/artwork/master/builtwith.png)](http://gulpjs.com)

## APIGEE MANUAL
  
  Usage: a127 [options] [command]

  Commands:

    account <action>
       manage deployment accounts
    
    project <action>
       manage a project
    
    service <action>
       manage services
    
    usergrid <action>
       manage Usergrid process
    
    config 
       print config
    
    wiki 
       load the apigee-127 wiki
    
    help [cmd]
       display help for [cmd]
    

  Options:

    -h, --help     output usage information
    -V, --version  output the version number

## First steps
  0) npm -g apigee-127
  
  1) a127 project create <PROJECT_NAME>
  
  2) cd <PROJECT_NAME>/
  
  3) sudo npm i
  
  4) a127 project start
  
  5) a127 project edit
  
  6) a127 account create <APIGEE_ACCOUNT_NAME>
  
  7) DEBUG=true a127 project deploy -u (use -u flag to solve an intermitent issue while uploading to apigee servers)
  
  8) apigeetool deploynodeapp -o YOUR_ORG -e test -u USERNAME -n APP_NAME -m app.js -d . -U -V


## Apigee-127
    Node server with Express 4 and Swagger specification based, an example API for bulking 
    data in a remote Elastic Search connected with Swagger for nice and easy API definition 
    schema-based, the great feature is that Swagger is installed as a dependency and Gulp 
    install it in our local for a plug-and-play usage, but also it generates the JS code based 
    on the schema definition of the API, so if you want to modify the output or input of 1 or 
    your API calls, you just change it manually in the Swagger UI, and Gulp will generate the 
    JS code of the API so you don;t have to touch code to change your API definitions, you will
    only have to change the business logic impacted with the change in your API.

## Features so far:
    1) Don't Swim in the mud! :Gulp building the JS for our API using the schema defined in the Swagger UI
    2) Failure Proof: CI-CD Using Travis, Gulp, Mocha, Code Climate and Istanbul, if there is any failure
       in a test or the Code Climate quality gets reduced by a pull request, the PR wont get merged. (TBF)

## To build Swagger:
    gulp swagger

    Additional info:
    The generated files will be in 'swagger' folder
    The generated file we will use in our API will be slapi.js, basically we will use it inside our
    Nodejs Express server, this is the business logic part, obviously we want to have the control here
    but we will not need to modify slapi.js touching the code because it is defined in Swagger, to modify
    it only go to Swagger UI (http://localhost:3002/index) and modify it, then do 'gulp swagger-code-gen'
    restart your server and the changes will be there

## To install this project:
    If you want the full version the best way is to execute install_prerequisites.sh
    If not you can simply do: 'npm i'

## Routing
    When you call your API, the middleware attempts to match a route defined in the Swagger file to a corresponding controller method. When you test your API, one of three possible results can occur:
    
        #A route defined in the Swagger file matches a controller file, and the controller has a method for the operation. In this case, either the route method is executed or, if you are in mock mode, a mock response is returned.
    
        #A route defined in the Swagger file matches a controller file, but there is no method in the controller for the operation. In this case, a 405 HTTP code is returned.
    
        #The requested route is not present in the Swagger file. In this case, a 404 code is returned.

## info sources
    http://jshint.com/blog/better-npm-integration/
    http://blog.oskoui-oskoui.com/?p=8478
    https://github.com/jscs-dev/gulp-jscs/
    http://docs.travis-ci.com/user/migrating-from-legacy/?utm_source=legacy-notice&utm_medium=banner&utm_campaign=legacy-upgrade
    http://ariya.ofilabs.com/2015/06/detecting-and-automatically-fixing-javascript-code-style.html
    http://ariya.ofilabs.com/2014/12/docker-and-phoenix-how-to-make-your-continuous-integration-more-awesome.html
    http://rhumaric.com/2014/01/livereload-magic-gulp-style/
    https://scotch.io/tutorials/a-quick-guide-to-using-livereload-with-gulp
    https://www.npmjs.com/package/swagger-ui
    https://www.browserling.com
    https://github.com/SBoudrias/gulp-istanbul
    http://developers-blog.helloreverb.com/enabling-oauth-with-swagger/
    https://github.com/swagger-api/swagger-spec/blob/master/versions/2.0.md#securityDefinitionsObject

    https://github.com/28msec/cellstore/tree/master/tasks
    
    APIGEE TUTORIAL:
    https://www.youtube.com/watch?v=KL1kAH2ipBw
    https://github.com/apigee-127/a127-documentation/wiki
    https://github.com/apigee-127/a127-documentation/wiki/Quick-Start:-Add-Quota
    https://github.com/apigee-127/a127-documentation/wiki/Quick-Start:-Add-a-New-Path
    https://github.com/apigee-127/a127-documentation/wiki/Quick-Start:-Add-Caching
    http://apigee.com/docs/app-services/content/installing-apigee-sdk-javascript




