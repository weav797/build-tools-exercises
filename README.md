# This project is for the Devops bootcamp exercise for 
## "Build Tools and Package Managers" <br /><br /><br />

This is a demonstration of my solution for the build tools exercises. Here are my solutions down below:<br /><br />

- [x] **EXERCISE 0: Clone project and create own Git repository**<br />
_To work with the project for the exercises:
Clone the project and
create your own project/git repository from it_<br />

```
Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github
$ **git clone --bare https://gitlab.com/twn-devops-bootcamp/latest/04-build-tools/build-tools-exercises.git**
Cloning into bare repository 'build-tools-exercises.git'...
remote: Enumerating objects: 276, done.
remote: Total 276 (delta 0), reused 0 (delta 0), pack-reused 276 (from 1)
Receiving objects: 100% (276/276), 15.58 MiB | 32.36 MiB/s, done.
Resolving deltas: 100% (72/72), done.

Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github
$ **cd build-tools-exercises.git**

Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github/build-tools-exercises.git (BARE:master)
$ **git remote set-url --push origin git@github.com:weav797/build-tools-exercises.git**

Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github/build-tools-exercises.git (BARE:master)
$ **git push --mirror**
Enumerating objects: 276, done.
Counting objects: 100% (276/276), done.
Delta compression using up to 16 threads
Compressing objects: 100% (123/123), done.
Writing objects: 100% (276/276), 15.58 MiB | 6.92 MiB/s, done.
Total 276 (delta 72), reused 276 (delta 72), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (72/72), done.
To github.com:weav797/build-tools-exercises.git
 * [new branch]      feature/solutions -> feature/solutions
 * [new branch]      master -> master

Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github
$ **rm -rf build-tools.exercises.git**

Orion@LAPTOP-7SLE0BV4 MINGW64 /d/projects/github
$ **git clone git@github.com:weav797/build-tools-exercises.git**
Cloning into 'build-tools-exercises'...
remote: Enumerating objects: 276, done.
remote: Counting objects: 100% (276/276), done.
remote: Compressing objects: 100% (123/123), done.
remote: Total 276 (delta 72), reused 276 (delta 72), pack-reused 0 (from 0)
Receiving objects: 100% (276/276), 15.58 MiB | 13.43 MiB/s, done.
Resolving deltas: 100% (72/72), done.


```
**Note:** I chose not to create a GitLab account since I already have most of my own repositories in GitHub, which is why you are seeing me clone from GitLab first, then creating/cloning the repo in GitHub.<br /><br />

- [x] **EXERCISE 1: Build jar artifact**<br />
_You want to deploy the artifact to share that library with all team members. So:_<br /><br />
_try to build the jar file_<br />
_The Build will fail, because of a compile error in a test, so you can't build the jar._<br />

```
D:\projects\github\build-tools-exercises>**gradle build**

> Task :compileTestJava FAILED
D:\projects\github\build-tools-exercises\src\test\java\AppTest.java:22: error: incompatible types: String cannot be converted to boolean
        boolean result = myApp.getCondition("true");
                                            ^
Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
1 error

[Incubating] Problems report is available at: file:///D:/projects/github/build-tools-exercises/build/reports/problems/problems-report.html

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileTestJava'.
> Compilation failed; see the compiler output below.
  D:\projects\github\build-tools-exercises\src\test\java\AppTest.java:22: error: incompatible types: String cannot be converted to boolean
          boolean result = myApp.getCondition("true");
                                              ^
  Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
  1 error

* Try:
> Check your code and dependencies to fix the compilation error(s)
> Run with --scan to get full insights.

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.13/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD FAILED in 3s
5 actionable tasks: 5 executed
```
<br />

- [x] **EXERCISE 2: Run tests**<br />
_Fix the test, by changing "true" string to true boolean.
Run gradle test to execute only the tests and check the fix._<br />

See changes [here](https://github.com/weav797/build-tools-exercises/commit/b4be79560d941df8752e33bccc7c5646a714de29).

```
D:\projects\github\build-tools-exercises>**gradle test**

[Incubating] Problems report is available at: file:///D:/projects/github/build-tools-exercises/build/reports/problems/problems-report.html

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.13/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD SUCCESSFUL in 2s
3 actionable tasks: 2 executed, 1 up-to-date
```
<br />

- [x] **EXERCISE 3: Clean and build App**<br />
_You fixed the test. Now:_<br /><br />
_clean the build folder with gradle clean and
try to build jar file again._<br />

```
D:\projects\github\build-tools-exercises>**gradle clean**

[Incubating] Problems report is available at: file:///D:/projects/github/build-tools-exercises/build/reports/problems/problems-report.html

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.13/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD SUCCESSFUL in 843ms
1 actionable task: 1 executed


D:\projects\github\build-tools-exercises>**gradle build**

[Incubating] Problems report is available at: file:///D:/projects/github/build-tools-exercises/build/reports/problems/problems-report.html

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.13/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD SUCCESSFUL in 2s
6 actionable tasks: 6 executed
```
<br />

- [x] **EXERCISE 4: Start application**<br />
_Start the jar file to test that the application runs successfully as a jar file_<br /><br />
_Start app with /build/libs java -jar app-1.0.jar_<br />
_**NOTE**: replace "app-1.0.jar" with the name of YOUR jar file_.<br /><br />

```
D:\projects\github\build-tools-exercises>**java -jar build/libs/build-tools-exercises-1.0-SNAPSHOT.jar **                              
                                                                                                                                   
  .   ____          _            __ _ _                                                                                            
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::       (v3.1.0-SNAPSHOT)

2025-03-26T16:33:02.237-06:00  INFO 27908 --- [           main] com.example.Application                  : Starting Application v1.
0-SNAPSHOT using Java 20.0.2.1 with PID 27908 (D:\projects\github\build-tools-exercises\build\libs\build-tools-exercises-1.0-SNAPSHOT.jar started by Orion in D:\projects\github\build-tools-exercises)
2025-03-26T16:33:02.239-06:00  INFO 27908 --- [           main] com.example.Application                  : No active profile set, falling back to 1 default profile: "default"
2025-03-26T16:33:03.033-06:00  INFO 27908 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2025-03-26T16:33:03.040-06:00  INFO 27908 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2025-03-26T16:33:03.041-06:00  INFO 27908 --- [           main] o.apache.catalina.core.StandardEngine    : Starting Servlet engine: [Apache Tomcat/10.1.8]
2025-03-26T16:33:03.101-06:00  INFO 27908 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2025-03-26T16:33:03.102-06:00  INFO 27908 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 816 ms
2025-03-26T16:33:03.139-06:00  INFO 27908 --- [           main] com.example.Application                  : Java app started
2025-03-26T16:33:03.261-06:00  INFO 27908 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page: ServletContext resource [/index.html]
2025-03-26T16:33:03.371-06:00  INFO 27908 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2025-03-26T16:33:03.382-06:00  INFO 27908 --- [           main] com.example.Application                  : Started Application in 1.44 seconds (process running for 1.812)

D:\projects\github\build-tools-exercises>^A^A
'' is not recognized as an internal or external command,
operable program or batch file.
```

- [x] **EXERCISE 5: Start App with 2 Parameters**<br />
_Now you want to add parameters to your application, so you and other users can pass different values on startup._<br /><br />
_Add parameter input to the Java code (see code snippet below, which you can copy)_<br />
_Rebuild the jar file_<br />
_Execute the jar file again with 2 params_<br /><br />

See changes [here](https://github.com/weav797/build-tools-exercises/commit/b4be79560d941df8752e33bccc7c5646a714de29).<br /><br />
```
D:\projects\github\build-tools-exercises>**java -jar build/libs/build-tools-exercises-1.0-SNAPSHOT.jar one two  **                                                                                                                                                                    
                                                                                                                                                                                                                                                                                  
  .   ____          _            __ _ _                                                                                                                                                                                                                                           
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::       (v3.1.0-SNAPSHOT)

2025-03-26T16:42:59.623-06:00  INFO 18120 --- [           main] com.example.Application                  : Starting Application v1.0-SNAPSHOT using Java 20.0.2.1 with PID 18120 (D:\projects\github\build-tools-exercises\build\libs\build-tools-exercises-1.0-SNAPSHOT.jar started by Orion in D:\projects\github\build-tools-exercises)
2025-03-26T16:42:59.626-06:00  INFO 18120 --- [           main] com.example.Application                  : No active profile set, falling back to 1 default profile: "default"
2025-03-26T16:43:00.435-06:00  INFO 18120 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2025-03-26T16:43:00.443-06:00  INFO 18120 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2025-03-26T16:43:00.444-06:00  INFO 18120 --- [           main] o.apache.catalina.core.StandardEngine    : Starting Servlet engine: [Apache Tomcat/10.1.8]
2025-03-26T16:43:00.501-06:00  INFO 18120 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2025-03-26T16:43:00.502-06:00  INFO 18120 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 834 ms
2025-03-26T16:43:00.537-06:00  INFO 18120 --- [           main] com.example.Application                  : Java app started
2025-03-26T16:43:00.665-06:00  INFO 18120 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page: ServletContext resource [/index.html]
2025-03-26T16:43:00.764-06:00  INFO 18120 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2025-03-26T16:43:00.776-06:00  INFO 18120 --- [           main] com.example.Application                  : Started Application in 1.458 seconds (process running for 1.813)
2025-03-26T16:43:00.778-06:00  INFO 18120 --- [           main] com.example.Application                  : **Application will start with the parameters one and two**
```
