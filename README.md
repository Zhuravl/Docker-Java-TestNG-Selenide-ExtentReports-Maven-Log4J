# The Usource Test Automation Framework Example
With executing the tests in the Docker containers

## To launch tests, execute command (from the project root directory):
```
Start the Docker daemon
docker-compose up
mvn clean test site -Durl=TARGET_URL -Dbrowser=BROWSER_NAME -Dversion=BROWSER_VERSION -Dtest=TESTS_SCOPE -Dtimeout=TIMEOUT -DthreadCount=THREAD_COUNT
Ctrl+C
docker-compose down
```

Where:
 Parameters for the API and UI tests:
 * TARGET_URL      - the target site URL
 * BROWSER_NAME    - target browser name ('chrome', 'firefox', 'ie', 'opera', or 'edge')
 * BROWSER_VERSION - browser version, optional (the latest by default)
 * TESTS_SCOPE     - test name(s) to execute (e.g. 'MyFirstTest' or 'MyFirstTest#firstMethod' or 'MyFirstTest#firstMethod+secondMethod' or 'MyFirstTest#firstMethod,MySecondTest#firstMethod')
 * TIMEOUT         - the MAX timeout value (in seconds), optional (15 sec by default)
 * THREAD_COUNT    - specify how many threads should be allocated for this execution, optional (1 thread by default)

## An example params for launching the example test using Chrome browser and the default params:
```
Start the Docker daemon
docker-compose up
mvn clean test site -Durl=https://usource.com.ua/ -Dbrowser=chrome -Dtest=ExampleTest,ExampleTwoTest,ExampleThreeTest -DthreadCount=3
Ctrl+C
docker-compose down
```

## Test Execution Report:

To get the execution report, use maven `site` command and find the result in the `target\test-report\report.html` file.

NOTE: It's required to install and add to the PATH:

- [Docker](https://www.docker.com/products/docker-desktop/);
- [Java](https://java.com/en/download/);
- [Maven](https://maven.apache.org/download.cgi).
 