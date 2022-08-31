`mkdir spring-service`{{exec}}

`cd spring-service`{{exec}}

`curl -o spring.zip https://start.spring.io/starter.zip?type=maven-project&language=java&bootVersion=2.7.3&baseDir=demo&groupId=com.example&artifactId=demo&name=demo&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.demo&packaging=jar&javaVersion=17`{{exec}}

`unzip spring.zip`{{exec}}

```shell
sudo apt-get update
sudo apt-get install bellsoft-java11
```{{exec}}

`./mvnw package`

`java -jar target/*.jar`{{exec}}
