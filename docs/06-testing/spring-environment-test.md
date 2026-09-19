# Spring Boot Development Environment Test Report

## 1\. Test Information

|Item|Details|
|-|-|
|Project|Supermarket Management System|
|Application|Server Application|
|Task|Task-3 - Test Spring Boot Development Environment|
|Test Document|`spring-environment-test.md`|
|Operating System|Windows 11|
|Development IDE|IntelliJ IDEA 2026.2.1|
|JDK Distribution|Eclipse Temurin|
|JDK Version|25.0.4 LTS|
|Build Tool|Gradle Wrapper|
|Gradle Version|9.7.1|
|Build Configuration|Gradle Kotlin DSL|
|Spring Boot Version|4.1.1|
|Spring Dependency|Spring Web|
|Application Packaging|JAR|

\---

## 2\. Test Objective

The objective of this test is to verify that the development environment
required for the Spring Boot Server Application is correctly installed,
configured, integrated, and operational.

The test verifies the following:

* JDK installation and configuration
* IntelliJ IDEA installation
* IntelliJ IDEA integration with JDK
* IntelliJ IDEA integration with Git
* Spring Boot project creation
* Gradle Wrapper operation
* Spring Boot project build
* Spring Boot application startup
* Embedded web server operation
* HTTP connectivity to the running application
* Application shutdown

REST API functionality is not tested in this task.

The REST API classes and endpoints will be implemented and tested in
**Task-4 - Implement and Test REST API Functions**.

\---

## 3\. JDK Verification

The JDK installation was verified from PowerShell using the following
commands:

```powershell
java --version
javac --version
$env:JAVA\\\_HOME
Test-Path $env:JAVA\\\_HOME
\\\& "$env:JAVA\\\_HOME\\\\bin\\\\java.exe" --version
```

### 3.1 Java Runtime Result

```text
openjdk 25.0.4 2026-07-21 LTS
OpenJDK Runtime Environment Temurin-25.0.4+7
OpenJDK 64-Bit Server VM Temurin-25.0.4+7
```

### 3.2 Java Compiler Result

```text
javac 25.0.4
```

### 3.3 JAVA\_HOME Result

```text
C:\\\\Program Files\\\\Eclipse Adoptium\\\\jdk-25.0.4.7-hotspot\\\\
```

The path was verified using:

```powershell
Test-Path $env:JAVA\\\_HOME
```

Result:

```text
True
```

Java was also executed directly through `JAVA\\\_HOME`:

```powershell
\\\& "$env:JAVA\\\_HOME\\\\bin\\\\java.exe" --version
```

The command successfully executed Eclipse Temurin OpenJDK 25.0.4.

### 3.4 JDK Test Results

|Test|Result|
|-|-|
|Java Runtime Available|Yes|
|Java Runtime Version|OpenJDK 25.0.4 LTS|
|Java Compiler Available|Yes|
|Java Compiler Version|javac 25.0.4|
|JDK Distribution|Eclipse Temurin|
|`JAVA\\\_HOME` Configured|Yes|
|`JAVA\\\_HOME` Path Exists|True|
|Java Executable through `JAVA\\\_HOME`|Successful|

**JDK Verification Status: PASS**

\---

## 4\. IntelliJ IDEA Verification

IntelliJ IDEA was successfully installed and launched.

The installed IntelliJ IDEA version was verified using:

```powershell
winget list --name "IntelliJ IDEA"
```

The installed version was:

```text
IntelliJ IDEA 2026.2.1
```

The installation is managed through JetBrains Toolbox.

**IntelliJ IDEA Installation Status: PASS**

\---

## 5\. IntelliJ IDEA Integration Verification

IntelliJ IDEA was verified for integration with both Git and the installed
JDK.

### 5.1 Git Integration

The Git executable configuration was checked through:

```text
Settings
    → Version Control
        → Git
```

IntelliJ IDEA successfully detected the installed Git executable.

The Git integration was tested using the IntelliJ Git configuration and
the IntelliJ integrated terminal.

The following commands can be used to verify Git from the IntelliJ
terminal:

```powershell
git --version
git status
git branch --show-current
git remote -v
```

The current Task-3 development branch was successfully recognized as:

```text
task/03-spring-environment
```

This confirms that IntelliJ IDEA can communicate with the existing Git
installation and recognize the project repository.

**Git Integration Status: PASS**

### 5.2 JDK Integration

The project JDK configuration was checked through:

```text
File
    → Project Structure
        → Project
```

The following configuration was detected:

|Setting|Result|
|-|-|
|Project SDK|Eclipse Temurin 25.0.4|
|Language Level|SDK Default|

The JDK was also verified through the IntelliJ integrated terminal using:

```powershell
java --version
javac --version
$env:JAVA\\\_HOME
Test-Path $env:JAVA\\\_HOME
```

The IntelliJ terminal successfully accessed the same JDK installed and
verified at the operating system level.

This confirms the integration path:

```text
Windows
   ↓
Eclipse Temurin JDK 25
   ↓
IntelliJ IDEA
   ↓
Project SDK
```

**JDK Integration Status: PASS**

\---

## 6\. Spring Boot Server Application Creation

A new Spring Boot Server Application was created inside the existing
Supermarket Management System repository.

The application was created in:

```text
supermarket-template/
└── server-app/
```

A separate Git repository was not created for `server-app`.

The Spring Boot application therefore remains part of the main
Supermarket project repository.

### 6.1 Spring Boot Project Configuration

The project was generated using Spring Initializr with the following
configuration:

|Setting|Value|
|-|-|
|Project Generator|Spring Initializr|
|Spring Initializr Server|`start.spring.io`|
|Name|`server-app`|
|Language|Java|
|Build System|Gradle|
|Gradle DSL|Kotlin|
|Group|`com.synoflux`|
|Artifact|`server-app`|
|Package Name|`com.synoflux.serverapp`|
|JDK|Eclipse Temurin 25.0.4|
|Java Version|25|
|Packaging|JAR|
|Spring Boot Version|4.1.1|
|Dependency|Spring Web|

### 6.2 Generated Application Structure

The generated application contains the Spring Boot source code,
configuration files, and Gradle Wrapper.

The main structure is:

```text
server-app/
│
├── gradle/
│   └── wrapper/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   └── resources/
│   │
│   └── test/
│
├── .gitattributes
├── .gitignore
├── build.gradle.kts
├── gradlew
├── gradlew.bat
└── settings.gradle.kts
```

The Gradle Wrapper is included with the project so that a separate global
Gradle installation is not required.

**Spring Boot Project Creation Status: PASS**

\---

## 7\. Gradle Wrapper Verification

The Gradle installation required by the project was verified using the
Gradle Wrapper.

The following command was executed from the `server-app` directory:

```powershell
.\\\\gradlew.bat --version
```

### 7.1 Gradle Verification Results

|Item|Result|
|-|-|
|Gradle Version|9.7.1|
|JVM|Eclipse Temurin 25.0.4 LTS|
|JDK Location|`C:\\\\Program Files\\\\Eclipse Adoptium\\\\jdk-25.0.4.7-hotspot`|
|Operating System|Windows 11 amd64|

The command executed successfully.

This confirms that the project can use its Gradle Wrapper without
requiring students to manually install Gradle globally.

The execution path is:

```text
gradlew.bat
     ↓
Gradle Wrapper
     ↓
Gradle 9.7.1
     ↓
JDK 25.0.4
```

**Gradle Wrapper Verification Status: PASS**

\---

## 8\. Spring Boot Build Test

The Spring Boot application was built using the Gradle Wrapper.

The following command was executed from the `server-app` directory:

```powershell
.\\\\gradlew.bat clean build
```

The build produced the following result:

```text
BUILD SUCCESSFUL in 8s
8 actionable tasks: 7 executed, 1 up-to-date
```

The successful build verifies that:

* The Gradle Wrapper is operational.
* Gradle can execute using JDK 25.
* The Spring Boot project configuration is valid.
* Required dependencies can be resolved.
* Java source code can be compiled.
* Test tasks can execute.
* The Spring Boot application can be packaged successfully.

The complete build chain was therefore verified as:

```text
server-app
     ↓
Gradle Wrapper
     ↓
Gradle 9.7.1
     ↓
JDK 25.0.4
     ↓
build.gradle.kts
     ↓
Spring Boot Dependencies
     ↓
Compile
     ↓
Test
     ↓
Package
     ↓
BUILD SUCCESSFUL
```

**Spring Boot Build Test Status: PASS**

\---

## 9\. Spring Boot Runtime Test

After successfully building the project, the Spring Boot application was
started using the Gradle Wrapper.

The following command was executed:

```powershell
.\\\\gradlew.bat bootRun
```

Spring Boot started successfully.

The application initialized the embedded web server and became available
through the local development environment.

The application was accessible through:

```text
http://localhost:8080
```

This verifies the runtime path:

```text
Gradle Wrapper
     ↓
Spring Boot
     ↓
Embedded Web Server
     ↓
Port 8080
     ↓
localhost:8080
```

**Spring Boot Runtime Test Status: PASS**

\---

## 10\. HTTP Connectivity Test

After starting the Spring Boot application, an HTTP request was made from
a web browser to:

```text
http://localhost:8080/employees
```

The application returned:

```text
Whitelabel Error Page

There was an unexpected error
(type=Not Found, status=404).
```

The HTTP `404 Not Found` response is expected during Task-3.

The response demonstrates that:

1. The browser successfully connected to `localhost:8080`.
2. The embedded web server was running.
3. The web server received the HTTP request.
4. The request reached the Spring Boot application.
5. No `/employees` endpoint currently exists.
6. Spring Boot therefore returned HTTP status `404 Not Found`.

The `Employee` model and `EmployeeController` REST endpoints have
intentionally not been implemented during Task-3.

They will be implemented and tested during Task-4.

### 10.1 HTTP Test Results

|Test|Result|
|-|-|
|Spring Boot Application Reachable|Yes|
|Embedded Web Server Reachable|Yes|
|Port 8080 Available|Yes|
|HTTP Request Received|Yes|
|`/employees` Endpoint Implemented|No|
|HTTP Response|404 Not Found|
|404 Expected During Task-3|Yes|

The HTTP 404 response is therefore not considered a failure of the
development environment.

It confirms that the web application is running while the requested REST
endpoint has not yet been implemented.

**HTTP Connectivity Test Status: PASS**

\---

## 11\. Application Shutdown Test

After completing the Spring Boot runtime and HTTP connectivity tests, the
application was stopped from the terminal.

The following keyboard command was used:

```text
Ctrl + C
```

The Spring Boot process terminated and control returned to the PowerShell
command prompt.

This confirms that the development server can be started and stopped
normally during application development.

**Application Shutdown Test Status: PASS**

\---

## 12\. Overall Test Results

|Test Area|Status|
|-|-|
|JDK Installation|PASS|
|JDK Configuration|PASS|
|Java Runtime|PASS|
|Java Compiler|PASS|
|`JAVA\\\_HOME` Configuration|PASS|
|IntelliJ IDEA Installation|PASS|
|IntelliJ IDEA and Git Integration|PASS|
|IntelliJ IDEA and JDK Integration|PASS|
|Spring Boot Project Creation|PASS|
|Gradle Wrapper Verification|PASS|
|Spring Boot Dependency Resolution|PASS|
|Spring Boot Build|PASS|
|Spring Boot Runtime|PASS|
|Embedded Web Server|PASS|
|HTTP Connectivity|PASS|
|Application Shutdown|PASS|

\---

## 13\. Final Result

### Overall Environment Test: PASS

The Spring Boot development environment has been successfully installed,
configured, integrated, and tested.

The environment can successfully:

1. Execute Java using Eclipse Temurin JDK 25.
2. Compile Java source code using `javac`.
3. Use IntelliJ IDEA as the development IDE.
4. Integrate IntelliJ IDEA with the installed JDK.
5. Integrate IntelliJ IDEA with Git.
6. Create a Spring Boot Server Application.
7. Use the Gradle Wrapper without requiring a global Gradle installation.
8. Resolve the required Spring Boot and Spring Web dependencies.
9. Compile and test the Spring Boot project.
10. Package the Spring Boot application.
11. Start the Spring Boot application.
12. Run the embedded web server on port 8080.
13. Receive HTTP requests through `localhost`.
14. Stop the Spring Boot development server correctly.

The following development environment has therefore been verified:

```text
Git
 │
 ├──────────────┐
 │              │
 ▼              ▼
IntelliJ IDEA   Repository
 │
 ▼
JDK 25
 │
 ▼
Spring Boot Project
 │
 ▼
Gradle Wrapper
 │
 ▼
Gradle 9.7.1
 │
 ▼
Spring Boot 4.1.1
 │
 ▼
Spring Web
 │
 ▼
Embedded Web Server
 │
 ▼
localhost:8080
```

The Spring Boot Server Application development environment is ready for
REST API development.

\---

## 14\. Next Task

**Task-4 - Implement and Test REST API Functions**

Task-4 will introduce the:

* `Employee` model
* `EmployeeController`
* REST API endpoints
* HTTP GET requests
* HTTP POST requests
* HTTP PUT requests
* HTTP DELETE requests
* REST API testing

The successful completion of Task-3 provides the verified development
environment required to begin Task-4.

