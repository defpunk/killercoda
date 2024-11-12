
Create a Dockerfile that lets us run containerDemo-0.0.1-SNAPSHOT.jar

<br>
<details><summary>Info</summary>
<br>

```plain
FROM openjdk:19-jdk
COPY containerDemo-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
```

</details>
