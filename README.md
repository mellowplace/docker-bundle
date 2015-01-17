# docker-bundle

The driver of this bundle is to be able to provide convenience methods when using [Docker](http://www.docker.com/) as your development environment and packaging tool.

At a minimum it should:

* Provide separate build, test, develop and run environments
* Provide convenience commands for managing the lifecycle of your dev container
* Provide convenience commands to package and commit your app to a repo

## Ideal commands

* `app/console docker:build`

  > Run configurable build commands (composer install, publish assets etc)

* `app/console docker:dev [start|stop|restart]`

  > Manage your development container (ports and dependencies provided by configuration)
  
* `app/console docker:package`

  > Runs a build and then packages the app with the prod Dockerfile

* `app/console docker:test`

  > Runs the testsuite inside the docker container, this is good for two reasons
  > 1. Your tests will run in an environment consistent with production
  > 2. If your tests require a database or other external system you can inject a throw
  >    away container that will mean your parameters.yml needs not differ for any 
  >    environment
