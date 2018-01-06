---
layout: post
title: "[GCE] Google Container Engine"
categories: [gce]
tags: [GCE, Google Container Engine]
description: Google Container Engine
---

# Google Container Engine

## install google cloud SDK
$ curl https://sdk.cloud.google.com | bash
$ exec -l $SHELL

## install kubernetes
$ gcloud components update kubectl

## docker start
$ docker-machine start default
$ docker-machine env default
$ eval "$(docker-machine env default)"

## shell
$ export GCE_PROJECT_ID="semy-1340"

## docker build
$ docker build -t gcr.io/${GCE_PROJECT_ID}/allim-rest .

## gcloud login
$ gcloud auth login

## gce push
$ gcloud docker push gcr.io/semy-1340/allim-rest

## cluster
$ gcloud container clusters create allim-rest-micro-cluster \
    --num-nodes 3 \
    --machine-type f1-micro

$ gcloud container clusters create allim-rest-samll-cluster \
    --num-nodes 1 \
    --machine-type g1-small

$ gcloud container clusters list
$ gcloud compute instances list

## pod
$ kubectl run allim-rest-small-pod --image=gcr.io/semy-1340/allim-rest --port=8080
deployment "allim-rest-small-pod" created
$ kubectl get pods
$ kubectl get no

## service
$ kubectl expose rc allim-rest-small --type="LoadBalancer"
$ kubectl describe rc
$ kubectl get svc
$ kubectl get services


# terminate
## delete service
$ kubectl delete services hello-node

## delete pod
$ kubectl delete pods allim-rest-micro-cluster-pod-3919680809-ke50s
$ kubectl delete pods --all

## delete cluster
$ gcloud container clusters delete allim-rest-samll-cluster



