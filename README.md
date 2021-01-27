# k8s-example
Kubernetes example

For this example we will use the [kind](https://kind.sigs.k8s.io/)

## Creating a cluster with kind

```shell
kind create cluster --name=k8s-example
```

## Setting owr cluster as context of kubectl

```shell
kubectl cluster-info --context kind-k8s-example
```

## Creating node app

```shell
docker run --rm -it -v $PWD:/app -w /app node npm init

docker run --rm -it -v $PWD:/app -w /app node npm install express --save

docker run --rm -it -v $PWD:/app -p 80:3000 -w /app node index
```

## Running pod.yaml

```shell
kubectl apply -f k8s/pod.yaml
```

### Testing pod before create a service

```shell
kubectl port-forward pod/frontend 3000:3000
```

### Deleting the pod

```shell
kubectl delete pod frontend
```

## Running the replicaset

```shell
kubectl apply -f k8s/replicaset.yaml
```

## Running the deployment

```shell
kubectl apply -f k8s/deployment.yaml
```

## Running service

```shell
kubectl apply -f k8s/service.yaml
```

### Forwarding port of service

```shell
kubectl port-forward svc/frontend-service 3000:3000
```


## Types of service

+ ClusterIP
+ LoadBalancer
