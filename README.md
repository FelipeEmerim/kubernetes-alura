# Kubernetes alura

Projeto para os estudos do curso de kubernetes da Alura

## Minikube

O projeto utiliza o minikube para realizar os experimentos.
Veja como instalar [aqui](https://minikube.sigs.k8s.io/docs/start/)

## Kubectl

O kubectl é obrigatório para interagir com o cluster
Veja como instalar [aqui](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

## Helm

O help é um 'gerenciador de pacotes' do kubernetes. Utilizado para habilitar addons como cert-manager e ingress e
instalar serviços como o rancher.
Veja como instalar [aqui](https://helm.sh/docs/intro/install/)
Caso use linux, veja se é possível utilizar package managers na sua distro

## Rancher

O rancher não é necessário, mas é uma UI interessante para visualizar e
gerenciar os componentes do kubernetes.
Veja como instalar rancher para desenvolvimento [aqui](https://rancher.com/docs/rancher/v2.x/en/installation/other-installation-methods/single-node-docker/)

## Aplicação

A aplicação é composta por 3 componentes.

* Um deployment do portal de notícias
* Um deployment para o sistema de notícias, com dois volumes: 1 para imagens e outro para sessão
* Um statefulset para o banco de dados com um volume e uma única réplica

```bash
kubectl apply -f volumes/minikube-st-class.yaml # Criar a classe de volumes primeiro
```

```bash
kubectl apply -f volumes
```

```bash
kubectl apply -f config-maps
```

```bash
kubectl apply -f services/svc-portal-noticias.yaml
kubectl apply -f services/svc-sistema-noticias.yaml
kubectl apply -f services/svc-db-noticias.yaml
```

```bash
kubectl apply -f deployments/portal-noticias-deployment.yaml
```

```bash
kubectl apply -f deployments/sistema-noticias-deployment.yaml
```

```bash
kubectl apply -f stateful-sets/db-noticias-deployment.yaml
```
