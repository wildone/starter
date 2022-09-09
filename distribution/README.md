# Luna distribution
It builds a Luna distribution containing all dependencies, configurations and running scripts (including WebSight and Howlite). 

The release artifacts are:
- `slingosgifeature` file (descriptor for all projects that extend our distribution)
- ICE Docker image.

## Prerequisites
- Java 17 & Maven
- Docker Desktop

## How to build

Run the command

```bash
mvn clean install
```

to assemble the distribution, build a Docker image and run integration tests.

## How to run
### Running as JVM application
```bash
mvn clean install
docker run -p 27017:27017 mongo:4.4.6
java -jar target/dependency/org.apache.sling.feature.launcher.jar -f target/slingfeature-tmp/feature-wsce-luna.json
```

and open [localhost:8080](http://localhost:8080/) to see the ICE admin panel (use default `wsadmin/wsadmin` password).

Press `CTRL + C` to stop the application.

## References
Please see the [Websight Starter docs](https://bitbucket.org/teamds-workspace/websight-starter).