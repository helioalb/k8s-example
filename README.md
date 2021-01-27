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

