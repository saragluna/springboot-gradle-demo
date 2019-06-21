# springboot-gradle-demo

## Gradle

- Step 1: Install gradle

  ```shell
  $ brew install gradle
  ```

- Step 2:  Make project

  ```shell
  $ mkdir springboot-gradle-demo
  $ cd springboot-gradle-demo
  $ gradle init
  ```

- Step 3: Edit build.gradle

  ```shell
  plugins {
      // Apply the java plugin to add support for Java
      id 'java'
      id 'idea'
      id 'org.springframework.boot' version '2.1.6.RELEASE'
  }
  
  apply plugin: 'java'
  apply plugin: 'idea'
  
  // When you apply the io.spring.dependency-management plugin, Spring Boot’s plugin will 
  // automatically import the spring-boot-dependencies bom from the version of Spring Boot 
  // that you are using
  apply plugin: 'io.spring.dependency-management'
  
  bootJar {
      baseName = 'springboot-demo'
      version = '0.1.0'
      mainClassName = 'springboot.gradle.demo.Application'
  }
  
  repositories {
      mavenCentral()
  }
  
  sourceCompatibility = 1.8
  targetCompatibility = 1.8
  
  dependencies {
      implementation 'org.springframework.boot:spring-boot-starter-web'
      implementation 'org.springframework.boot:spring-boot-starter-actuator'
      testImplementation 'junit:junit:4.12'
  }
  ```

- Step 4: build

  ```shell
  $ ./gradlew build
  ```

- Step 5: Open project in IDEA

  ```shell
  $ ./gradlew idea
  $ ./gradlew openIdea
  ```

  

