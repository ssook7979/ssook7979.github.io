# 9. Maven Build LIfecycles

> A lifecycle is a pre-defined group of build steps called phases.
> 

> Each phase can be bound to one or more plugin goals
> 

> All work done in Maven is done by plugins
> 

> Lifecycles and phases provide the framework to **call plugin goals** in a sequence
> 

# Pre-defined lifecycles

- clean
- default
- site

Clean lifecycle

pre-clean → clean(plugin binding) → post-clean

Maven Clean Plugin

Goal: clean

# Default Lifecycle- High-level

- validate
- Compile
- Test
- Package
- Verify- Run Integration Tests
- Install
- Deploy

# Default Lifecycle - JAR Packaging

[https://maven.apache.org/ref/3.8.6/maven-core/default-bindings.html](https://maven.apache.org/ref/3.8.6/maven-core/default-bindings.html)

# Site Build Lifecycle

[https://maven.apache.org/ref/3.8.6/maven-core/lifecycles.html#site-lifecycle](https://maven.apache.org/ref/3.8.6/maven-core/lifecycles.html#site-lifecycle)