# bedrock-hello-world-helm

## Application
Uses a publicly available image built from
[bedrock-hello-world](https://github.com/digitalbazaar/bedrock-hello-world).

## Prerequisites
- Provision a Kubernetes cluster on the cloud of choice.
- The `kubectl` command-line tool installed on your local machine and configured
  to connect to your cluster. Instructions for installing `kubectl` are in
  the [official documentation](https://kubernetes.io/docs/tasks/tools/).
- The `helm` command-line tool  installed on your local machine. Instructions
  for installing `helm` are in the
  [official documentation](https://github.com/helm/helm/releases).
- Install and configure
  [ingress-nginx](https://kubernetes.github.io/ingress-nginx/).

## Deploy
```sh
git clone https://github.com/digitalbazaar/bedrock-hello-world-helm.git
cd bedrock-hello-world-helm

kubectl create namespace bedrock-hello-world
helm upgrade --debug --install --wait --timeout 5m --namespace bedrock-hello-world -f values.yaml qa bedrock-hello-world

curl -k https://<load-balancer-ip>/hello-world
# Hello World from Kubernetes!
```
