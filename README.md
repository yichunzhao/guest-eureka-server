## Why using Eureka? 

Netflix-Eureka provides an fixed point for services to register themselves, and therefore can be discovered by other services, by this way communicate with each other and without hard-coding hostname and port. 

* Providing both a console and a discovery platform for registering and identifying all of your services wihtin a distributed system. 
* Eureka was created and open sourced by Netflix
* providing a Rest-based service to consume the discovery platform itself
* default round-robin load balancing client, 
* it is easy to integrate with Spring for the entire project was open-sourced by Eureka.  
* Euerka server now much like a config server; having a built-in and easy to use dashboard

## Major elements

* Eureka server, a service registry working like a fixed point linking all services. 
* Eureka client, a Rest service which registers itself at the registry (Eureka Server). 
* A web application, consuming Rest services as a registry-aware client(Spring cloud netflix Feign Client)

## Eureka-server

Boot starter: Spring cloud Discovery and then select Eureka server

@EnableEurekaServer at the main application class

Configuring application properties:  8761 is a default for Eureka server; meanwhile we tell the built-in Eureka client don't register youself as a client, for we works as a sever.  

>server.port = 8761
>eureka.client.register-with-eureka=false
>eureka.client-fetch-registry=false

* It works like a Config Server; 
* Clean rest-interface for registration and discovery.
* Easy built-in dashboard supprts replication

## Services are registered with Eureka
Eureka console: http://localhost:8761  Eureka server dashboard shows registered services and their instances, and their health status. 

![image](https://user-images.githubusercontent.com/17804600/88575617-75be9800-d044-11ea-890d-862947c8a453.png)


## Eureka Client

For a SpringBootApplication to be discovery-aware, we have to include some Spring Discovery Client into class path.

Add pom dependency: spring-cloud-starter-netflix-eureka-client
go to application class: add @EnableDiscoveryClient

* leverages spring.application.name
* works much like a Config client 


## Consuming services with Ribbon


## Consuming service via Feign interface

Using Eureka through Feign with Ribon 

Building an interface at the consumption side that matching the inface at the service, by this way you wired across the boundary

Add pom dependency: 

````
spring-cloud-starter-openfeign
````

Main application class; @EnableFeignClients

creating a Fein client interface



