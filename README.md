# heroku-buildpack-takipi

This buildpack is in addition to buildpack for JVM specific language needed to run your application.
We support the 
[Java](https://github.com/heroku/heroku-buildpack-java),
[Scala](https://github.com/heroku/heroku-buildpack-scala), [Clojure](https://github.com/heroku/heroku-buildpack-clojure),
[Gradle](https://github.com/heroku/heroku-buildpack-gradle), [Grails](https://github.com/heroku/heroku-buildpack-grails)
 and [Play!](https://github.com/heroku/heroku-buildpack-play) default buildpacks.
 
 ### Install Takipi

In order to use this buildpack enter the directory of your app.

For a new app (If you already have a running app - go ahead the next level):
By default, Heroku will choose the best buildpack for your app automatically. But in many cases, you will need to explicitly define the JVM specific language buildpack: 

`heroku create myapp --buildpack <Here_insert_the_buildpack_link>`

 Once you have a running app run:

`heroku buildpacks:add https://github.com/takipi/heroku-buildpack-takipi.git`

### Setup Takipi

Once your app is configured to run Takipi, either add [Takipi addon](https://addons.heroku.com/takipi) or setup Takipi manually:

1. Create an account at https://app.takipi.com/account.html
2. Run : `heroku config:get TAKIPI_SECRET_KEY`
2. Run `heroku config:set TAKIPI_SECRET_KEY=S193#...` with the key received in the previous step.
 

