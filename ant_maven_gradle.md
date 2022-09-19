[https://www.baeldung.com/ant-maven-gradle](https://www.baeldung.com/ant-maven-gradle)

# Intro

Java build automation tools

# Ant

- Another Neat Tool
- can be used for building non-Java applications
- initially part of Apache Tomcat codebase
- released as a standalone project in 2000
- Apache Ivy was developed later for dependency management
    - As this is not part of built-in supprot of Ant, the needs of built-in dependency management system grew.
- flexible, but everything had to be written from scratch
- build steps name is “targets”

# Maven

- a dependency management and a build automation tool for Java applications(as noted on official pages)
- ✔️ **Maven can be considered a plugin execution framework, since all work is done by plugins**
- **Maven relies on conventions and provides predefined commands (goals)**
    - let user focus on specific build goals
    - provides the framework for the goal
- provided built-in support for **dependency management**
- No need to define basic phases
    - Maven has them already as a default build phases
- less flexible than Ant
    - Goal customization is very hard
    - This lead to the creation of Gradle
- build steps name is “phases”

# Gradle

- use a DSL(Domain Specific Language) based either on Groovy or Kotlin
    - not XML format
    - smaller configuration files
    - build.gradle(Groovy), build.gradle.kts(Kotlin)
- like Maven, plugins add all useful features
- tasks
- example

build.gradle

```powershell
apply plugin: 'java'

repositories {
    mavenCentral()
}

jar {
    baseName = 'gradleExample'
    version = '0.0.1-SNAPSHOT'
}

dependencies {
    testImplementation 'junit:junit:4.12'
}
```

prompt

```powershell
gradle classes
```

In this example, a build is done by java plugin