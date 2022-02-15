# kubernets-Helm-Chart

## Helm Chart

Helm Chart is an application package manager for the kubernetes cluster, just like we have apt packager manager in Linux.

So what can we do with Helm Chart -

* Define k8s application
* Install k8s application
* Upgrade k8s application

Most important aspect of the Helm Chart is you do not have to use Kubernetes CLI(command line interface) and neither you need to remember complex kubernetes commands to manage the kubernetes manifest.

## 1 Install Helm Chart

Using Script

```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
```
```
chmod 700 get_helm.sh
```
```
./get_helm.sh
```
Verify Helm Chart Installation
```
which helm
```

## 2 create Our First Helm Chart

Before we create a our First Helm Chart, we need to have kubernetes cluster up and running. Use the following command to verify the status of kubernetes cluster -
```
kubectl get all
```
```
NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.233.0.1   <none>        443/TCP   27d
```

lets run some Helm Commands for creating our first Helm Chart
```
helm create springboot
```

## 3. Helm Chart Structure

Run the following command to see the tree structure of our Springboot Helm Chart -

```
tree springboot
```
```
springboot
├── Chart.yaml
├── charts
├── templates
│ ├── NOTES.txt
│ ├── _helpers.tpl
│ ├── deployment.yaml
│ ├── hpa.yaml
│ ├── ingress.yaml
│ ├── service.yaml
│ ├── serviceaccount.yaml
│ └── tests
│     └── test-connection.yaml
└── values.yaml
```
In the next section we will go through each YAML configuration

### Chart.yaml
This file contains all the metadata about our Helm Chart for example -

```
apiVersion: v2 #mandatory
name: springboot #mandatory
description: A Helm chart for Kubernetes
type: application
version: 0.1.0 #mandatory
appVersion: 1.16.0
```
1 apiVersion
2 name
3 version
Other configurations are optional

Versioning - Each chart should has its own version number and it should follow the Semantic Versioning

### values.yaml
 
This configuration file holds values for the configuration.
































https://jhooq.com/building-first-helm-chart-with-spring-boot/
