# S04T01N02 - Spring Boot Introduction with Gradle

## Description

This project is a basic Spring Boot REST API created using **Gradle** as the build tool. It introduces how to set up a Spring Boot application with a simple controller and how to run it using basic Gradle commands.

---

## Project Metadata

- **Group:** `cat.itacademy.s04.t01.n02`
- **Artifact:** `S04T01N02`
- **Name:** `S04T01N02`
- **Description:** `S04T01N02`
- **Package name:** `cat.itacademy.s04.t01.n02`
- **Packaging:** `Jar`
- **Java Version:** 11 or higher

---

## Dependencies

- Spring Web
- Spring Boot DevTools

---

## Setup Instructions

### 1. Generate the Project

Go to [https://start.spring.io](https://start.spring.io) and configure the project with the above metadata, using **Gradle** as the dependency manager.

### 2. Import into Eclipse

Import the project using:
```
File > Import > Existing Gradle Project
```

---

### 3. Configuration

Edit the `src/main/resources/application.properties` file and add the following:

```properties
server.port=9001
```

---

## API Endpoints

A package named `controller` should be created under the base package. Inside, add a class named `HelloWorldController` with two GET methods:

### 1. `/HelloWorld` – RequestParam Version

```java
    @GetMapping("/HelloWorld")
    public String hello(@RequestParam(value = "name", defaultValue = "UNKNOWN") String name) {
        return "Hello "+ name +". You are executing a Maven project.";
```

- **Example URLs:**
  - `http://localhost:9001/HelloWorld`
  - `http://localhost:9001/HelloWorld?name=El meu nom`

---

### 2. `/HelloWorld2/{nom}` – PathVariable Version

```java
    @GetMapping({"/HelloWorld2", "/HelloWorld2/{name}"})
    public String hello2(@PathVariable(required = false) String name) {
        if (name == null) {
            name = "UNKNOWN";
        }
        return "Hello "+ name +". You are executing a Maven project.";
    }
```

- **Example URLs:**
  - `http://localhost:9001/HelloWorld2`
  - `http://localhost:9001/HelloWorld2/name`

---

## Gradle Commands

Open a terminal and navigate to the root of the project directory. Run the following commands:

| Command           | Description                     |
|------------------|---------------------------------|
| `gradle build`   | Compile the project              |
| `gradle assemble`| Package the application (JAR)    |
| `gradle clean`   | Clean previous builds            |
| `gradle bootRun` | Run the application              |

> Ensure that Gradle is installed and added to your system's PATH.

---


