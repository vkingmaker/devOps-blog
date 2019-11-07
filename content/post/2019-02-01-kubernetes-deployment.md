---
title: First Kubernetes Deployment
date: 2019-02-01
tags: ['kubernetes', 'code']
---

First application on Kubernetes using Kubernetes deployments

<!--more-->

```sh
    $ kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080
```

Now, check whether it is running:

```sh
    $ kubectl get pods
    NAME                                   READY     STATUS    RESTARTS   AGE
    kubernetes-bootcamp-5c69669756-wv2rp   1/1       Running   0          11s
```

We can check application logs:

```sh
$ kubectl logs kubernetes-bootcamp-5c69669756-wv2rp
Kubernetes Bootcamp App Started At: 2018-10-20T13:38:41.537Z | Running On:  kubernetes-bootcamp-5c69669756-wv2rp
```

---

title: Scaling My Kubernetes Deployment
date: 2019-02-02
tags: ["kubernetes", "code"]

---

Scaling my Kubernetes deployment

<!--more-->

'''sh
\$ kubectl scale deployments/kubernetes-bootcamp --replicas=4
'''

Now, check whether it is scaled up:

'''sh
\$ kubectl get deployments
NAME DESIRED CURRENT UP-TO-DATE AVAILABLE AGE
kubernetes-bootcamp 4 4 4 4 26s

    $ kubectl get pods -o wide
    NAME                                   READY     STATUS    RESTARTS   AGE       IP           NODE
    kubernetes-bootcamp-5c69669756-9jhz9   1/1       Running   0          3s        172.18.0.7   minikube
    kubernetes-bootcamp-5c69669756-lrjwz   1/1       Running   0          3s        172.18.0.5   minikube
    kubernetes-bootcamp-5c69669756-slht6   1/1       Running   0          3s        172.18.0.6   minikube
    kubernetes-bootcamp-5c69669756-t4pcs   1/1       Running   0          28s       172.18.0.4   minikube

'''
