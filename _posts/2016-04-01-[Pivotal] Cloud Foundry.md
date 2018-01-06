---
layout: post
title: "[Pivotal] Cloud Foundry"
categories: [pivotal]
tags: [pivotal, cloud foundry]
description: 
---

### Login
```
$ cf login [-a API_URL] [-u USERNAME] [-p PASSWORD] [-o ORG] [-s SPACE] .

API_URL: This is your API endpoint, the URL of the Cloud Controller in your Cloud Foundry instance.
USERNAME: Your username.
PASSWORD: Your password. Use of the -p option is discouraged as it may record your password in your shell history.
ORG: The org where you want to deploy your apps.
SPACE: The space in the org where you want to deploy your apps.

ex) $ cf login -s development
```

### Cloud Foundry
```
$ yo jhipster:cloudfoundry
```


### After application modification, repackage it with
```
$ ./mvnw package -DskipTests=true -B -Pdev
```

### And then re-deploy it with
```
$ cf push -f ./deploy/cloudfoundry/manifest.yml -p target/*.war
```

### Environment
```
$ cf env spring-music
```

### Restage
```
$ cf restage spring-music
```

### Delete 
```
$ cf d spring-music

Really delete the app spring-music?> y
Deleting app spring-music in org oreilly-class / space instructor as mstine@pivotal.io...
OK

$ cf ds spring-music-db

Really delete the service spring-music-db?> y
Deleting service spring-music-db in org oreilly-class / space instructor as mstine@pivotal.io...
OK
```