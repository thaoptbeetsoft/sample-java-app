# SAMPLE JAVA APPLICATION
### 1. Tech stack
- java 8
- Spring boot 2.6.4
- Spring boot security
- Spring boot jwt
- Spring boot jpa
- Spring boot actuator
- MySQL 8.0.28
- Swagger 3.0
- Docker
- Grafana & Prometheus

### 2. Getting started

2.1 build docker images
>$ mvn clean install
> 
>$ docker-compose up -d --build

2.2 Test
>$ curl --location --request POST http://localhost:8080/api/v1/auth/login --header Authorization:Basic b2F1dGgyQ2xpZW50Om9hdXRoMlNlY3JldA== --header Content-Type:application/x-www-form-urlencoded --data-urlencode username=sysadmin --data-urlencode password=password

2.3 View API information by Swagger

Visit Swagger:  [Swagger UI](http://localhost:8080/api/v1/swagger-ui.html)


2.4 Check Application Health
>$ curl --location --request GET http://localhost:8099/actuator

2.5 Update Code and ReRun
>$ mvn clean install
> 
>$ docker-compose up -d --build api-service

2.6 View api-service container log
>$ docker-compose logs -tf api-service

2.7 Remote Debug
>Connect port 5005

2.8 Log and Monitoring API-Service
    
- Monitoring and alert: [Prometheus Target](http://localhost:9090/targets)
- Prometheus web UI: [Prometheus Graph](http://localhost:9090/graph)
- Grafana web UI: [Grafana](http://localhost:3000)
  - default account: admin/admin
    
 

###3 Push Images to Docker Hub (Reverse to deploy on EC2)
**3.1 On Local**
- Create docker tag
>$  docker tag sample-java-app_api-service luongquoctay87/sample-java-app:v1.0.0
- Push to Docker Hub
>$ docker login
> 
>$ docker push luongquoctay87/sample-java-app:v1.0.0
**3.2 On EC2**

  - Install docker
  - Pull image and run by docker-compose.dev.yml
