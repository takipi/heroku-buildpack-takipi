# heroku-buildpack-takipi

This buildpack is used to Install Takipi on a working Heroku JVM application (Java, Scala, Gradle, Clojure, Grails, Play).
Configuring Takipi is a quick 3 steps: provision, install and connect. 

### Provisioning
The heroku add-on is now deprecated. 
In order to provision Heroku:
1. Sign up for OverOps to get an installation key (e.g. S1#11#13f#affa)
2. Add the installation key as an environment variable named `TAKIPI_SECRET_KEY`

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

Rebuild your app to finalize the setup.

You're all done! Head to https://app.takipi.com to see the magic.

Questions? E-Mail hello@takipi.com.

www.takipi.com
