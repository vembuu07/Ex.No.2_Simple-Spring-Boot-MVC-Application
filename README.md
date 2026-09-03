# Name: Vembarasan P
# Reg No: 212223220123
# Exp_2_Simple-Spring-Boot-MVC-Application

## Aim

To develop a simple Spring Boot MVC (Model-View-Controller) application that uses a controller to handle HTTP requests, a model to pass data, and a view (Thymeleaf) to render dynamic HTML pages.

## Algorithm

1. Create a new Spring Boot project using Spring Initializr.
2. Add the following dependencies:
    - Spring Web
    - Thymeleaf
3. Set up the project structure:
    - Create the main class annotated with `@SpringBootApplication`.
    - Create a controller class using `@Controller`.
    - Add HTML templates under `src/main/resources/templates`.
4. Create a controller:
    - Define a method to handle HTTP GET requests using `@GetMapping`.
    - Return a view name (HTML page name) from the controller.
    - Pass data to the view using the `Model` object.
5. Create a model, if needed:
    - Define a simple POJO class if you need to pass structured data to the view.
6. Create view pages using Thymeleaf:
    - Create an HTML file inside the templates folder.
    - Use Thymeleaf syntax such as `${name}` to render dynamic content.
7. Run the application from your IDE or command line.
8. Open a browser and navigate to http://localhost:8080/.

## Program

```text
spring-mvc-demo/
├── src/
│   └── main/
│       ├── java/
│       │   └── com.example.mvc/
│       │       ├── MvcApplication.java
│       │       └── HomeController.java
│       └── resources/
│           ├── templates/
│           │   └── index.html
│           └── application.properties
└── pom.xml
```

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>4.0.6</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.example</groupId>
	<artifactId>mvc</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>mvc</name>
	<description/>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf-test</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>

```

### MvcApplication.java

```java
package com.example.mvc;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MvcApplication {

	public static void main(String[] args) {
		SpringApplication.run(MvcApplication.class, args);
	}

}
```

### HomeController.java

```java
package com.example.mvc;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {
        model.addAttribute("message", "Welcome to Spring Boot MVC!");
        return "index";
    }
}
```

### index.html

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
	<head>
		<title>Spring MVC</title>
	</head>
	<body>
		<h1 th:text="${message}">Default Message</h1>
	</body>
</html>
```

### application.properties

```properties
spring.application.name=mvc
```

## Output

![img.png](img.png)

## Result

Thus the development of a simple Spring Boot MVC application is completed successfully
