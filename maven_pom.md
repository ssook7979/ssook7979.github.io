# 6. Maven POM

# POM

- Project Object Model
- `XML` doc
- a description of a Maven Project
- use the `maven-4.0.0.xsd` schema
- can inherit properties from a parent POM
    - sub-modules also inherit
    - e.g. Spring Boot
- `Effective POM` is the POM complete with inherited properties
- `mvn help:effective-pom`