---
layout: post
title: "[kubernetes] GKE"
categories: [kubernetes]
tags: [kubernetes, microservice, gke]
description: microservice
---

### install 
* https://cloud.google.com/sdk/
```
$ gcloud components install kubectl
```

### Create a Docker container image
```
$ docker build -t gcr.io/PROJECT_ID/gateway:v1 .
```

### Run Docker
```
$ docker run -d -p 8080:8080 gcr.io/PROJECT_ID/gateway:v1
```

### Push to the Google Container Registry
```
$ gcloud docker push gcr.io/PROJECT_ID/gateway:v1
```

### Create cluster
```
$ gcloud container clusters get-credentials hello-world
$ kubectl cluster-info
$ gcloud container clusters describe hello-world
```

### Create pod
```
$ kubectl run gateway-node --image=gcr.io/PROJECT_ID/gateway:v1 --port=8080
$ kubectl get deployments
$ kubectl get pods
```

### log
```
$ kubectl logs <POD-NAME>
```

### cluster command
```
$ kubectl cluster-info
$ dkubectl get events
$ kubectl config view
```



* http://kubernetes.io/docs/hellonode/