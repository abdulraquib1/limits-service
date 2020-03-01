
# Spring Cloud : Limits-Service
 
** Demonstrates reading properties from application.properties **
** Uses Springboot 2.2.4.RELEASE **
** Limits Service Port 8080 **


```
* Multiple instances of Limit Service can load the config changes from spring
* cloud config server rather than changing and bundling in each server

```

** Configuration **

```
# applicaiton.properties
spring.application.name=limits-service
limits-service.maximum=9999
limits-service.minimum=99

```

** In order to pickup configuration from Spring Cloud Config Server ***

```
#Rename applicaiton.properties to bootstrap.properties

spring.application.name=limits-service
spring.cloud.config.uri=http://localhost:8888
#if no profiles added, default profile is pickedup
spring.profiles.active=qa

```


** Annotations **

```
@Component
@ConfigurationProperties("limits-service")
public class Configuration { }

```

* open browser with [http://localhost:8080/limits](http://localhost:8080/limits) 



** References **

[Spring properties reference](https://docs.spring.io/spring-boot/docs/current/reference/html/common-application-properties.html)

[MD File Syntax](https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html)

[In28mins Github Resource Config](https://github.com/in28minutes/spring-microservices/tree/master/03.microservices)
[Install Github on local](https://git-scm.com/)

