# 1. Java Compile

# Java Compile Process

source file

java, groovy, scala, kt ⇒ class ⇒ JVM Runtime

class

platform independent byte source file

jvm 

platform dependent runner

# Packaging Java Application

## Process

classes —( Zip Compression )→ jar, war, ear —( Unzip )—>JVM

## Packaging

jar 

- Java ARchive
- typically not a complete application

war 

- Web Application aRchive
- typically a complete application
- deployed to application servers (Tomcat/Webboss, websphere etc)

ear 

- Enterprise aRchive - zip file containing many war files
- typically a complete application
- deployed to application servers (Tomcat/Webboss, websphere etc)

fat jar(Uber JAR) 

- executable jar containing all dependencies(used by Spring Boot)
- can be deployed stand alone
- microservices

docker container 

- docker image containning runtime environment, JVM, Java package

# Java Compile

```powershell
javac HelloWorld.java

java HelloWorld
```

Jar Packaging

```powershell
jar cf myjar.jar HelloWorld.class HelloWorld2.class
or
jar cf myjar.jar *.class
```

Jar 구조

```powershell
PS D:\dev\test\myjar> Get-ChildItem | tree /f
work 볼륨에 대한 폴더 경로의 목록입니다.
볼륨 일련 번호는 38BD-47F7입니다.
D:.
│  HelloWorld.class
│  HelloWorld2.class
│
└─META-INF
        MANIFEST.MF
```

class 실행

```powershell
java -classpath myjar.jar HelloWorld
```

using third party library

```powershell
javac --classpath ./lib/* HelloWorld
java --classpath ./lib/* HelloWorld
```