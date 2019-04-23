# Setting up your Spring project

## Spring Initializr
A great way to get started with a Spring boot application is by visiting the [https://start.spring.io/](Spring Initializr website) and choose the following options:
* Project: `Gradle Project`
* Language: `Kotlin`
* Spring Boot: `2.1.4`
* Group: `com.instructure.budapest`
* Artifact: `codelabs`
* Dependencies: `Web`

Click `Generate Project` and save/extract the downloaded zip file.

## JUnit5 and Mockito
Locate your `build.gradle` file and add the following dependencies:
```groovy
    testImplementation('org.junit.jupiter:junit-jupiter-api:5.2.0')
    testImplementation('org.junit.jupiter:junit-jupiter-params:5.2.0')
    testImplementation "org.mockito:mockito-core:2.+"
    testImplementation('org.mockito:mockito-junit-jupiter:2.18.3')
	testImplementation('io.kotlintest:kotlintest-assertions:3.3.2')
    testRuntime('org.junit.jupiter:junit-jupiter-engine:5.2.0')
```

We need to enable Gradle's JUnit5 support:
```groovy
test {
    useJUnitPlatform()
}
```

Now you have your base `SpringBootApplication` set up with all the required dependencies in your `build.gradle` file.

## Checkpoint acceptance criteria
Run the tests with `./gradlew test` and afterwards run the application with `./gradlew bootRun` to confirm you have everything set up correctly. You should get a similar output:
```bash
$ ./gradlew test
BUILD SUCCESSFUL in 1s
4 actionable tasks: 4 up-to-date

$ ./gradlew bootRun
> Task :bootRun

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.4.RELEASE)

2019-04-23 12:52:47.151  INFO 48085 --- [           main] c.i.bp.codelabs.CodelabsApplicationKt    : Starting CodelabsApplicationKt on jpollak-l.corp.instructure.com with PID 48085 (/Users/jpollak/repos/codelabs/todo-spring/chkpoint1-setting-up-a-spring-project/build/classes/kotlin/main started by jpollak in /Users/jpollak/repos/codelabs/todo-spring/chkpoint1-setting-up-a-spring-project)
2019-04-23 12:52:47.153  INFO 48085 --- [           main] c.i.bp.codelabs.CodelabsApplicationKt    : No active profile set, falling back to default profiles: default
2019-04-23 12:52:48.126  INFO 48085 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-04-23 12:52:48.154  INFO 48085 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-04-23 12:52:48.154  INFO 48085 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.17]
2019-04-23 12:52:48.308  INFO 48085 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-04-23 12:52:48.308  INFO 48085 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1110 ms
2019-04-23 12:52:48.495  INFO 48085 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2019-04-23 12:52:48.665  INFO 48085 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-04-23 12:52:48.668  INFO 48085 --- [           main] c.i.bp.codelabs.CodelabsApplicationKt    : Started CodelabsApplicationKt in 1.852 seconds (JVM running for 2.171)
<==========---> 80% EXECUTING [10s]
> :bootRun

```