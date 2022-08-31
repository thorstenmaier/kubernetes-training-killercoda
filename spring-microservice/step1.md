`curl -o demo.zip "https://start.spring.io/starter.zip?type=maven-project&language=java&bootVersion=2.7.3&baseDir=demo&groupId=com.example&artifactId=demo&name=demo&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.demo&packaging=jar&javaVersion=17&dependencies=web,data-jpa,h2,data-rest,data-rest-explorer"`{{exec}}

`unzip demo.zip`{{exec}}

`cd demo`{{exec}}

`touch src/main/java/com/example/demo/Auto.java`{{exec}}

`nano src/main/java/com/example/demo/Auto.java`{{exec}}

```java
package com.example.demo;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.Id;

@Entity
public class Auto {

    @Id
    @GeneratedValue
    private Long id;

    private String marke;

    private String modell;

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getMarke() {
        return marke;
    }

    public void setMarke(String marke) {
        this.marke = marke;
    }

    public String getModell() {
        return modell;
    }

    public void setModell(String modell) {
        this.modell = modell;
    }

    @Override
    public String toString() {
        return "Auto{" +
                "id=" + id +
                ", marke='" + marke + '\'' +
                ", modell='" + modell + '\'' +
                '}';
    }
}
```{{copy}}

`touch src/main/java/com/example/demo/AutoRepository.java`{{exec}}

`nano src/main/java/com/example/demo/AutoRepository.java`{{exec}}

```java
package com.example.demo;

import org.springframework.data.jpa.repository.JpaRepository;

public interface AutoRepository extends JpaRepository<Auto, Long> {
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

{{TRAFFIC_HOST1_8080}}

`./mvnw spring-boot:build-image`{{exec}}
