`mkdir spring-service`{{exec}}

`cd spring-service`{{exec}}

`curl -o spring.zip "https://start.spring.io/starter.zip?type=maven-project&language=java&bootVersion=2.7.3&baseDir=demo&groupId=com.example&artifactId=demo&name=demo&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.demo&packaging=jar&javaVersion=17&dependencies=web"`{{exec}}

`unzip spring.zip`{{exec}}

`nano src/main/java/com/example/demo/MyController.java`{{exec}}

```java
package com.example.demo;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class MyController {
        @GetMapping("/")
        public String hello() {
                return "Hello from Spring";
        }
}
```{{copy}}

```shell
wget -q -O - https://download.bell-sw.com/pki/GPG-KEY-bellsoft | sudo apt-key add -
echo "deb [arch=amd64] https://apt.bell-sw.com/ stable main" | sudo tee /etc/apt/sources.list.d/bellsoft.list
```{{exec}}

```shell
sudo apt-get update
sudo apt-get install bellsoft-java17
```{{exec}}

`./mvnw package`{{exec}}

`java -jar target/*.jar`{{exec}}
