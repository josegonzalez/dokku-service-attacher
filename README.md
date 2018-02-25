# dokku service attacher

[EXPERIMENTAL] Creates and links a dokku service if an app's docker-compose.yml has the correct label.

## requirements

- dokku 0.4.x+
- docker 1.8.x

## installation

```shell
# on 0.4.x+
sudo dokku plugin:install https://github.com/josegonzalez/dokku-service-attacher.git service-attacher
```

## usage

On application deploy, if the following are true:

- the application has not had a successful deploy yet
- there is a `docker-compose.yml` in the repository base
- there is a label in the form of `dokku.service.SERVICE_NAME=SOME_NAME`

This plugin will:

- create the service (with the same name as the current application)
- attach the service to the application

If the service exists or is already attached, nothing will happen.

> The SOME_NAME is reserved for future use, but is currently ignored.
