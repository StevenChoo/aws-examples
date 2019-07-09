# BeanStalk Java Jetty Maven Example

A simple Java & Jetty application using the [BeanStalk Maven Plugin](http://beanstalker.ingenieux.com.br/beanstalk-maven-plugin/) for automatically create and deploy the application on AWS BeanStalk

## Prequisitions

## Info

This example is based on the following AWS provided [example](https://aws.amazon.com/blogs/developer/deploying-java-applications-on-elastic-beanstalk-from-maven/).
It uses the [BeanStalk Maven Plugin](http://beanstalker.ingenieux.com.br/beanstalk-maven-plugin/) to automatically deploy a Java application using the BeanStalk stack

## Maven

### Plugin options

[Options](http://beanstalker.ingenieux.com.br/beanstalk-maven-plugin/plugin-info.html)

## Instructions

### Deploy

1. go to root of project
2. update project settings in pom.xml 
    ```xml
    <!-- 
        Change the maven groupId and artifactId.The AWS BeanStalk config is derived from the artifactId.
    -->
    <groupId>Your maven groupId</groupId>
    <artifactId>Your maven artifactId</artifactId>
    ```
3. update AWS settings in pom.xml. For all options check the Maven plugin info page, [Options](http://beanstalker.ingenieux.com.br/beanstalk-maven-plugin/plugin-info.html)
    ```xml
    <beanstalker.region>Your AWS region</beanstalker.region>
    ```
4. run
    ```bash
    mvn -Ps3-deploy package deploy
    ```

### Undeploy
