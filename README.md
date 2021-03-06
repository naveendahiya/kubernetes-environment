# kubernetes-environment

The goal of this project is to have some examples using [`Kubernetes`](https://kubernetes.io) ([`Minikube`](https://github.com/kubernetes/minikube)) 

## Prerequisites

- **Tools**

  You must have the following tools installed

  | Tool            | Version I used in the last commit     | Command to check   |
  | --------------- | ------------------------------------- | ------------------ |
  | [`Kubectl`][1]  | Client: `v1.18.6`; Server: `v1.18.3`  | `kubectl version`  |
  | [`Minikube`][2] | `v1.12.1`                             | `minikube version` |
  | [`Helm`][3]     | `v3.2.4`                              | `helm version`     |
  | [`Java 11+`][4] | `11.0.7`                              | `java --version`   |
  | [`Docker`][5]   | Client: `19.03.12`; Server: `19.03.12`| `docker version`   |
  
  [1]:https://kubernetes.io/docs/tasks/tools/install-kubectl/
  [2]:https://kubernetes.io/docs/tasks/tools/install-minikube/
  [3]:https://helm.sh/docs/intro/install/
  [4]:https://www.oracle.com/java/technologies/javase-jdk11-downloads.html
  [5]:https://www.docker.com/

- **Helm Chart Repositories**

  You must have the following `repo`'s added in your helm chart repository list.
  ```
  NAME        	URL
  stable      	https://kubernetes-charts.storage.googleapis.com/
  codecentric 	https://codecentric.github.io/helm-charts/
  kong        	https://charts.konghq.com
  bitnami     	https://charts.bitnami.com/bitnami
  elastic     	https://helm.elastic.co
  ```

  In order to check it, run
  ```
  helm repo list
  ```

  If some of them is missing, here are the commands to add
  ```
  helm repo add stable https://kubernetes-charts.storage.googleapis.com/
  helm repo add codecentric https://codecentric.github.io/helm-charts/
  helm repo add kong https://charts.konghq.com
  helm repo add bitnami https://charts.bitnami.com/bitnami
  helm repo add elastic https://helm.elastic.co
  ```
  
  Run the command below to get the latest information about charts from the chart repositories
  ```
  helm repo update
  ```

## Examples

- ### [author-book-review-graphql](https://github.com/ivangfr/kubernetes-environment/tree/master/author-book-review-graphql#kubernetes-environment)
- ### [book-service-kong-keycloak](https://github.com/ivangfr/kubernetes-environment/tree/master/book-service-kong-keycloak#kubernetes-environment)
- ### [user-event-sourcing-kafka](https://github.com/ivangfr/kubernetes-environment/tree/master/user-event-sourcing-kafka#kubernetes-environment)
- ### [movies-api-elk-prometheus-grafana](https://github.com/ivangfr/kubernetes-environment/tree/master/movies-api-elk-prometheus-grafana#kubernetes-environment)

## Start Minikube

- Open a terminal and start `Minikube` by running the following command. The properties `--memory` and `--vm-driver` are optional
  ```
  minikube start --memory='8000mb' --vm-driver='virtualbox'
  ```

- Run the command below to get the latest information about charts from the chart repositories
  ```
  helm repo update
  ``` 

## Shutdown Minikube

The following command shuts down the `Minikube Virtual Machine`, but preserves all cluster state and data. Starting the cluster again will restore it to its previous state.
```
minikube stop
```

The command shuts down and deletes the `Minikube Virtual Machine`. No data or state is preserved.
```
minikube delete
```
