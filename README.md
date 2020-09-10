## Why using Eureka? 

* Providing both a console and a discovery platform for registering and identifying all of your services wihtin a distributed system. 
* Eureka was created and open sourced by Netflix
* providing a Rest-based service to consume the discovery platform itself
* default round-robin load balancing client, 
* it is easy to integrate with Spring for the entire project was open-sourced by Eureka.  
* Euerka server now much like a config server; having a built-in and easy to use dashboard

## Eureka-server

Boot starter: Spring cloud Discovery and then select Eureka server

@EnableEurekaServer

server.port = 8761

Eureka.client.register-with-Eureka=false

eureka.client-fetch-registry=false

* It is much like a Config Server
* Clean rest-interface for registration and discovery
* Easy built-in dashboard supprts replication

## Eureka Client

* leverages spring.application.name
* works much like a Config client 

Add pom dependency: spring-cloud-starter-netflix-eureka-client
go to application class: add @EnableDiscoveryClient

## Services are registered with Eureka
Eureka console

![image](https://user-images.githubusercontent.com/17804600/88575617-75be9800-d044-11ea-890d-862947c8a453.png)

## Consuming services with Ribbon


