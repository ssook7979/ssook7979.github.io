# 3. Maven Coordinates

# Maven Coordinates

- used to identify artifacts
- coordinate
    - groupId
    - artifactId
    - version
- groupId and version can be **inherited** from a parent POM

## groupId

- Typically, the unique identifier of org
    - Typically the org’s reverse domain

## artifactId

- typically, the project name, a descriptor for the artifact

## version

- a version of the project

### version naming

```powershell
(( Major )).(( Minor )).(( Incremental V - patch )).(( Build Number )).(( Qualifier ))
```

- build number - from CI build
- qualifier - string qualifier - ‘beta’ …
- major.minor.incre is most common

### SNAPSHOT suffix

- tells Maven that this is a development version(Not stable)
- dependency에 있으면 maven은 local repository를 검색한 후 remote 검색
- 만일 SNAPSHOT 버전이 검색이 되면 newer version을 검색 시도함
- By default, Maven will check remote repositories once per day