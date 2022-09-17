# Intro

- wrapper around maven that allows work with maven without install it

# Purpose

- make your build portable and self contained

# Create mvnw

```powershell
mvn -N io.takari:maven:wrapper -Dmaven=3.6.0
```

option N

> N,--non-recursive Do not recurse into sub-projects
> 

-Dmaven=3.6.0

optional, specify version of maven

## 폴더 구조

.mvn

-wrapper