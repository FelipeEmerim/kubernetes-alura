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

## Instalando o portal de notícias

```bash
helm install portal-noticias helm/portal-noticias
```

## Instalando o sistema de notícias

Crie um arquivo dentro de helm/sistema-noticias chamado `.env.yaml`, copie a chave `env:` de values.yaml e preencha os valores em branco.
Após isso, basta rodar o comando abaixo:
*O arquivo .env.yaml é apenas um arquivo para sobrescrever valores padrão do helm.*

```bash
helm install sistema-noticias -f helm/sistema-noticias/.env.yaml helm/sistema-noticias/
```

## Instalando o banco de dados de notícias

Crie um arquivo dentro de helm/db-noticias chamado `.env.yaml`, copie a chave `env:` de values.yaml e preencha os valores em branco.
Após isso, basta rodar o comando abaixo:
*O arquivo .env.yaml é apenas um arquivo para sobrescrever valores padrão do helm.*

```bash
helm install db-noticias -f helm/db-noticias/.env.yaml helm/db-noticias/
```


## Desinstalar um componente

Basta utilizar o comando uninstall do helm e o nome do componente. Por exemplo:

```bash
helm uninstall sistema-noticias
```
