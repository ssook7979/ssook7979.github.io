# 7. Dependencies

# Dependency

typically a **jar** or **pom**

# Types

## Transitive Dependency

> A dependency of an artifact which your project depends on. Can go MANY layers deep. Cyclic dependencies are not supported
> 

## Dependency Mediation

> Determines what version to use when multiple versions of the same dependency are encountered.
> 

> ‘**Nearest Definition**’ in dependency tree is used.
> 
- **Nearest Definition →** generally latest

> Example: a → b; a → d 2.0; b → d 1.5 then, d version 2.0 would be included
> 

## Excluded Dependencies

## Optional Dependencies

> excluded by default for downstream projects
> 

# Scope

- Compile
    - Default
    - Available on all classpaths of project
    - propagated to downstream
- Provided
    - expected to be provided by JDK or container at runtime
- Runtime
    - Not required for compile, but needed for runtime
    - On runtime and test classpaths, not compile
- Test
    - Only available on test classpath, not transitive
- System
    - Similar to provided, but JAR is added to system explicitly via file path
- Import
    - Imports dependency of POM
    - e.g. standardize versions of specific dependencies

# Dependency Plugin

- Dependencies are managed by the `Maven Dependency Plugin`.

## Important Goals

- dependency: tree
- dependency:go-offline
- dependency:purge-local-repository
- dependency:sources