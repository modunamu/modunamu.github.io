---
layout: post
title: "[Pivotal] Jhipster Microservice on Cloud Foundry"
categories: [pivotal, jhipster, microservice]
tags: [pivotal, cloud foundry, jhipster, microservice]
description: 
---

### Cloud Foundry
```
$ yo jhipster:cloudfoundry
```

### manifest.yml
```
---
path: .
memory: 256M
instances: 1
buildpack: https://github.com/cloudfoundry/java-buildpack
services:
applications:
- name: gateway
  host: gateway-${random-word}
  env:
    SPRING_PROFILES_ACTIVE: prod, cloudfoundry
  path: target/*.war
```

### application-prod.yml
```
eureka:
    instance:
        prefer-ip-address: false
        hostname: ${vcap.application.uris[0]}
    client:
        enabled: true
        healthcheck:
            enabled: true
        registerWithEureka: true
        fetchRegistry: true
        serviceUrl:
            #defaultZone: http://admin:adminuser@localhost:8761/eureka/
            defaultZone: http://admin:adminuser@jhipsterregistry-intuitional-ceanothus.cfapps.io/eureka/
```


### bootstrap-prod.yml
```
spring:
    cloud:
        config:
            fail-fast: true
            retry:
                initial-interval: 1000
                max-interval: 2000
                max-attempts: 100
            #uri: http://admin:adminuser@localhost:8761/config
            uri: http://admin:adminuser@jhipsterregistry-intuitional-ceanothus.cfapps.io/config
            # name of the config server's property source (file.yml) that we want to use
            name: gateway
            profile: prod # profile(s) of the property source
            label: master # toggle to switch to a different version of the configuration as stored in git
            # it can be set to any label, branch or commit of the config source git repository
```

### And then re-deploy it with
```
$ cf push -f ./deploy/cloudfoundry/manifest.yml -p target/*.war
```

* https://jhipster.github.io/cloudfoundry/
* https://jhipster.github.io/microservices-architecture/#cloudfoundry