# 2. compiling and packaging with maven

# packaging

java source file은 `src/main/java/` 이하에 위치해야 한다.

```powershell
// clean and packaging
mvn clean package
```

*class, META-INF 생성

# clean

```powershell
// remove target directory
mvn clean
```

# dependencies

compile time dependencies

```powershell
<dependencies>
	<dependency>
		<groupId></groupId>
		<artifactId></artifactId>
		<version></version>
	</dependency>
</dependencies>
```