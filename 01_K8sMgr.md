---
layout: lecture
title: "Manage Kubernetes Application"
date: 2020-05-03
ready: true
video:
  aspect:
  id:
---

{% comment %}
[Configure for containers](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)
{% endcomment %}

# Kubernetes Applications
## Defined by yaml files
## Different resources
- Deployment/ReplicaSet/Job...
- Service/ConfigMap/Secret
- RBAC/ServiceAccount
## Challenge
- Share application to others
*Customization*
*Versioning*
*Complexity*

- Multiple environment management
*Duplicated files*

# Helm
- The package manager for K8s.
- The best way to find, share and use software to build in K8s.
- Feature: Manage complexity, easy update, simple sharing, rollbacks. 
`K8s rollback: Pod. Helm roback: Application(all yamls)`

## Helm 3
- Simplify architecture
- Release are now scoped to namespaces
- Pushing charts to OCI registries

```console
$ sudo snap install helm --classic
2020-05-04T01:05:26Z INFO Waiting for restart...
helm 3.2.0 from Snapcrafters installed
$ helm version
version.BuildInfo{Version:"v3.2.0", GitCommit:"e11b7ce3b12db2941e90399e874513fbd24bcb71", GitTreeState:"clean", GoVersion:"go1.13.10"}
$ helm create test
Creating test
$ ls -ltr test/
total 16
-rw-r--r-- 1 vagrant vagrant 1794 May  4 01:07 values.yaml
drwxr-xr-x 3 vagrant vagrant 4096 May  4 01:07 templates
-rw-r--r-- 1 vagrant vagrant 1095 May  4 01:07 Chart.yaml
drwxr-xr-x 2 vagrant vagrant 4096 May  4 01:07 charts
$ cd test/
$ less 
charts/      Chart.yaml   .helmignore  templates/   values.yaml  
$ ls templates/
deployment.yaml  _helpers.tpl  hpa.yaml  ingress.yaml  NOTES.txt  serviceaccount.yaml  service.yaml  tests
$ helm install test .
NAME: test
LAST DEPLOYED: Mon May  4 01:10:50 2020
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=test,app.kubernetes.io/instance=test" -o jsonpath="{.items[0].metadata.name}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl --namespace default port-forward $POD_NAME 8080:80
$ kubectl get pods
NAME                         READY   STATUS    RESTARTS   AGE
test-69b4bd5bf4-qz8wl        1/1     Running   0          2m19s
$ kubectl get service
NAME         TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
test         ClusterIP   10.96.204.253   <none>        80/TCP         2m33s
$ kubectl get ingress
No resources found in default namespace.
$ helm list
NAME    NAMESPACE       REVISION        UPDATED                                 STATUS          CHART           APP VERSION
test    default         1               2020-05-04 01:10:50.885327634 +0000 UTC deployed        test-0.1.0      1.16.0     
vagrant@k8s-dev:~/ken/cicd/application/test$ cd templates/
vagrant@k8s-dev:~/ken/cicd/application/test/templates$ helm repo add stable https://kubernetes-charts.storage.googleapis.com/
"stable" has been added to your repositories
vagrant@k8s-dev:~/ken/cicd/application/test/templates$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "stable" chart repository
Update Complete. ⎈ Happy Helming!⎈ 
vagrant@k8s-dev:~/ken/cicd/application/test/templates$ helm repo list
NAME    URL                                              
stable  https://kubernetes-charts.storage.googleapis.com/
$ sudo docker run -dp 5000:5000 --restart=always --name registry registry
Unable to find image 'registry:latest' locally
latest: Pulling from library/registry
486039affc0a: Pull complete 
ba51a3b098e6: Pull complete 
8bb4c43d6c8e: Pull complete 
6f5f453e5f2d: Pull complete 
42bc10b72f42: Pull complete 
Digest: sha256:7d081088e4bfd632a88e3f3bcd9e007ef44a796fddfe3261407a3f9f04abe1e7
Status: Downloaded newer image for registry:latest
06df96480846a722c4576ae4a0e446935712b2553c67c2f1611338ca1286da98
vagrant@k8s-dev:~/ken/cicd/application/helm$ sudo docker ps
CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS                       NAMES
06df96480846        registry               "/entrypoint.sh /etc…"   28 seconds ago      Up 27 seconds       0.0.0.0:5000->5000/tcp      registry
6f17f30b9e6f        kindest/node:v1.17.0   "/usr/local/bin/entr…"   42 hours ago        Up 42 hours                                     kind-worker
e0bf64912bde        kindest/node:v1.17.0   "/usr/local/bin/entr…"   42 hours ago        Up 42 hours                                     kind-worker2
617a84022558        kindest/node:v1.17.0   "/usr/local/bin/entr…"   42 hours ago        Up 42 hours         127.0.0.1:32768->6443/tcp   kind-control-plane
$ sudo docker logs -f registry
time="2020-05-04T01:35:46.045191619Z" level=warning msg="No HTTP secret provided - generated random secret. This may cause problems with uploads if multiple registries are behind a load-balancer. To provide a shared secret, fill in http.secret in the configuration file or set the REGISTRY_HTTP_SECRET environment variable." go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.04528571Z" level=info msg="redis not configured" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.045408412Z" level=info msg="Starting upload purge in 24m0s" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.052191922Z" level=info msg="using inmemory blob descriptor cache" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.052539717Z" level=info msg="listening on [::]:5000" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
^C
vagrant@k8s-dev:~/ken/cicd/application/helm$ helm chart save . localhost:5000/myrepo/mychart:1.1.0
Error: this feature has been marked as experimental and is not enabled by default. Please set HELM_EXPERIMENTAL_OCI=1 in your environment to use this feature
vagrant@k8s-dev:~/ken/cicd/application/helm$ export HELM_EXPERIMENTAL_OCI=1
vagrant@k8s-dev:~/ken/cicd/application/helm$ helm chart save . localhost:5000/myrepo/mychart:1.1.0
ref:     localhost:5000/myrepo/mychart:1.1.0
digest:  8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e
size:    1.2 KiB
name:    cicd-app
version: 0.1.0
1.1.0: saved
vagrant@k8s-dev:~/ken/cicd/application/helm$ helm chart list
REF                                     NAME            VERSION DIGEST  SIZE    CREATED   
localhost:5000/myrepo/mychart:1.1.0     cicd-app        0.1.0   8e01cc4 1.2 KiB 31 seconds
vagrant@k8s-dev:~/ken/cicd/application/helm$ helm chart push localhost:5000/myrepo/mychart:1.1.0
The push refers to repository [localhost:5000/myrepo/mychart]
ref:     localhost:5000/myrepo/mychart:1.1.0
digest:  8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e
size:    1.2 KiB
name:    cicd-app
version: 0.1.0
1.1.0: pushed to remote (1 layer, 1.2 KiB total)
vagrant@k8s-dev:~/ken/cicd/application/helm$ sudo docker logs -f registry
time="2020-05-04T01:35:46.045191619Z" level=warning msg="No HTTP secret provided - generated random secret. This may cause problems with uploads if multiple registries are behind a load-balancer. To provide a shared secret, fill in http.secret in the configuration file or set the REGISTRY_HTTP_SECRET environment variable." go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.04528571Z" level=info msg="redis not configured" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.045408412Z" level=info msg="Starting upload purge in 24m0s" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.052191922Z" level=info msg="using inmemory blob descriptor cache" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:35:46.052539717Z" level=info msg="listening on [::]:5000" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
time="2020-05-04T01:59:46.048056028Z" level=info msg="PurgeUploads starting: olderThan=2020-04-27 01:59:46.047932006 +0000 UTC m=-603359.933725111, actuallyDelete=true" 
time="2020-05-04T01:59:46.048372993Z" level=info msg="Purge uploads finished.  Num deleted=0, num errors=1" 
time="2020-05-04T01:59:46.04838834Z" level=info msg="Starting upload purge in 24h0m0s" go.version=go1.11.2 instance.id=83ccfc39-be91-4b75-bc08-bf6fa0b10c1b service=registry version=v2.7.1 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "HEAD /v2/myrepo/mychart/blobs/sha256:6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f HTTP/1.1" 404 157 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:40.937341082Z" level=error msg="response completed with error" err.code="blob unknown" err.detail=sha256:6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f err.message="blob unknown to registry" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=86e40dec-0521-4c89-8c1a-4c0f8e76a29a http.request.method=HEAD http.request.remoteaddr="172.18.0.1:48668" http.request.uri="/v2/myrepo/mychart/blobs/sha256:6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f" http.request.useragent="containerd/1.3.2+unknown" http.response.contenttype="application/json; charset=utf-8" http.response.duration=2.203424ms http.response.status=404 http.response.written=157 vars.digest="sha256:6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f" vars.name="myrepo/mychart" 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "HEAD /v2/myrepo/mychart/blobs/sha256:8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e HTTP/1.1" 404 157 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:40.938799915Z" level=error msg="response completed with error" err.code="blob unknown" err.detail=sha256:8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e err.message="blob unknown to registry" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=db5cd6dc-6cc2-4aed-85d1-31912f100946 http.request.method=HEAD http.request.remoteaddr="172.18.0.1:48670" http.request.uri="/v2/myrepo/mychart/blobs/sha256:8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e" http.request.useragent="containerd/1.3.2+unknown" http.response.contenttype="application/json; charset=utf-8" http.response.duration="844.625µs" http.response.status=404 http.response.written=157 vars.digest="sha256:8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e" vars.name="myrepo/mychart" 
time="2020-05-04T06:10:40.964836535Z" level=info msg="response completed" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=ec2e091d-4b3c-4712-9e86-8223183e8db3 http.request.method=POST http.request.remoteaddr="172.18.0.1:48668" http.request.uri="/v2/myrepo/mychart/blobs/uploads/" http.request.useragent="containerd/1.3.2+unknown" http.response.duration=25.736389ms http.response.status=202 http.response.written=0 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "POST /v2/myrepo/mychart/blobs/uploads/ HTTP/1.1" 202 0 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:40.96773866Z" level=info msg="response completed" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=97ad9d16-17e7-4dd9-972d-17e080a51653 http.request.method=POST http.request.remoteaddr="172.18.0.1:48670" http.request.uri="/v2/myrepo/mychart/blobs/uploads/" http.request.useragent="containerd/1.3.2+unknown" http.response.duration=27.262418ms http.response.status=202 http.response.written=0 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "POST /v2/myrepo/mychart/blobs/uploads/ HTTP/1.1" 202 0 "" "containerd/1.3.2+unknown"
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "PUT /v2/myrepo/mychart/blobs/uploads/51607c79-5b0c-4f08-a335-fd4c58caeedd?_state=tLNXZYyfVtCooqXae5SGx6vieLJXLdtPB2rH40rp_3B7Ik5hbWUiOiJteXJlcG8vbXljaGFydCIsIlVVSUQiOiI1MTYwN2M3OS01YjBjLTRmMDgtYTMzNS1mZDRjNThjYWVlZGQiLCJPZmZzZXQiOjAsIlN0YXJ0ZWRBdCI6IjIwMjAtMDUtMDRUMDY6MTA6NDAuOTM5NjQ4MjIyWiJ9&digest=sha256%3A6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f HTTP/1.1" 201 0 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:40.973788541Z" level=info msg="response completed" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=9df64969-3cb8-437c-bb70-2b46dac1843b http.request.method=PUT http.request.remoteaddr="172.18.0.1:48668" http.request.uri="/v2/myrepo/mychart/blobs/uploads/51607c79-5b0c-4f08-a335-fd4c58caeedd?_state=tLNXZYyfVtCooqXae5SGx6vieLJXLdtPB2rH40rp_3B7Ik5hbWUiOiJteXJlcG8vbXljaGFydCIsIlVVSUQiOiI1MTYwN2M3OS01YjBjLTRmMDgtYTMzNS1mZDRjNThjYWVlZGQiLCJPZmZzZXQiOjAsIlN0YXJ0ZWRBdCI6IjIwMjAtMDUtMDRUMDY6MTA6NDAuOTM5NjQ4MjIyWiJ9&digest=sha256%3A6044c82339665f959eeec71471f601ca40e1cc37ed0aad1c4c576011a871091f" http.request.useragent="containerd/1.3.2+unknown" http.response.duration=7.947186ms http.response.status=201 http.response.written=0 
time="2020-05-04T06:10:40.986736555Z" level=info msg="response completed" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=2428c1ab-6aa8-408f-b9a3-b2b818832bad http.request.method=PUT http.request.remoteaddr="172.18.0.1:48670" http.request.uri="/v2/myrepo/mychart/blobs/uploads/92e0fb5f-af43-4d94-983c-38140333eee3?_state=i4160kcfmLBvXKz2fX2pa1SEjprLFKmNE3eu8LG494V7Ik5hbWUiOiJteXJlcG8vbXljaGFydCIsIlVVSUQiOiI5MmUwZmI1Zi1hZjQzLTRkOTQtOTgzYy0zODE0MDMzM2VlZTMiLCJPZmZzZXQiOjAsIlN0YXJ0ZWRBdCI6IjIwMjAtMDUtMDRUMDY6MTA6NDAuOTQxMzQzODc3WiJ9&digest=sha256%3A8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e" http.request.useragent="containerd/1.3.2+unknown" http.response.duration=17.15538ms http.response.status=201 http.response.written=0 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "PUT /v2/myrepo/mychart/blobs/uploads/92e0fb5f-af43-4d94-983c-38140333eee3?_state=i4160kcfmLBvXKz2fX2pa1SEjprLFKmNE3eu8LG494V7Ik5hbWUiOiJteXJlcG8vbXljaGFydCIsIlVVSUQiOiI5MmUwZmI1Zi1hZjQzLTRkOTQtOTgzYy0zODE0MDMzM2VlZTMiLCJPZmZzZXQiOjAsIlN0YXJ0ZWRBdCI6IjIwMjAtMDUtMDRUMDY6MTA6NDAuOTQxMzQzODc3WiJ9&digest=sha256%3A8e01cc4a0a3ac025f7608e3d996b7d7c9858d9b16466c34bd3bd69d145e1983e HTTP/1.1" 201 0 "" "containerd/1.3.2+unknown"
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "HEAD /v2/myrepo/mychart/manifests/1.1.0 HTTP/1.1" 404 95 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:40.993047372Z" level=error msg="response completed with error" err.code="manifest unknown" err.detail="unknown tag=1.1.0" err.message="manifest unknown" go.version=go1.11.2 http.request.host="localhost:5000" http.request.id=eb106444-16f0-4059-839a-38f93860693f http.request.method=HEAD http.request.remoteaddr="172.18.0.1:48670" http.request.uri="/v2/myrepo/mychart/manifests/1.1.0" http.request.useragent="containerd/1.3.2+unknown" http.response.contenttype="application/json; charset=utf-8" http.response.duration=1.450036ms http.response.status=404 http.response.written=95 vars.name="myrepo/mychart" vars.reference=1.1.0 
172.18.0.1 - - [04/May/2020:06:10:40 +0000] "PUT /v2/myrepo/mychart/manifests/1.1.0 HTTP/1.1" 201 0 "" "containerd/1.3.2+unknown"
time="2020-05-04T06:10:41.017618241Z" level=info msg="response completed" go.version=go1.11.2 http.request.contenttype="application/vnd.oci.image.manifest.v1+json" http.request.host="localhost:5000" http.request.id=d40f5ef5-2b67-4eba-bbc5-e5ded0be1a6b http.request.method=PUT http.request.remoteaddr="172.18.0.1:48670" http.request.uri="/v2/myrepo/mychart/manifests/1.1.0" http.request.useragent="containerd/1.3.2+unknown" http.response.duration=23.234015ms http.response.status=201 http.response.written=0 
```