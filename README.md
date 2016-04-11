# heroku-buildpack-takipi

This buildpack is used to Install Takipi on a working Heroku JVM application (Java, Scala, Gradle, Clojure, Grails, Play).
Configuring Takipi is a quick 3 steps: provision, install and connect. 

### Provisioning

Using the CLi, add the Takipi Heroku addon:
```
heroku addons:create takipi:lite
```
You can also use the Heroku dashboard to achieve the same. Have a look [here](https://elements.heroku.com/addons/takipi).
 
### Installation

In order to use this buildpack enter the directory of your app.

For a new app (If you already have a running app - go ahead the next level):
By default, Heroku will choose the best buildpack for your app automatically. But in many cases, you will need to explicitly define the JVM specific language buildpack: 

`heroku buildpacks:add https://github.com/takipi/heroku-buildpack-takipi.git`

### Connecting Takipi

Takipi needs to attach to your Java process by adding `-agentlib:TakipiAgent` jvm argument. 
Your Procfile should resemble this sample:

```
web: java $JAVA_OPTS -agentlib:TakipiAgent -jar target/dependency/jetty-runner.jar --port $PORT target/*.war
```

Questions? E-Mail hello@takipi.com.

www.takipi.com
