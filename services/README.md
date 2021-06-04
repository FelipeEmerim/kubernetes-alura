# Services

Services são formas de acessar Pods no kubernetes. Eles possuem 3 principais usos:
* Definir acesso na rede interna através de um IP fixo
* Definir acesso em uma porta fixa, a todos os nodes de um cluster
* Realizar balanceamento de carga utilizando um cloud provider ou internamente

## Cluster IP

Serviços do tipo ClusterIp definem um ip fixo para acessar pods. Dessa forma é possível acessar um pod de maneira previsível através do DNS da rede interna do kubernetes nas portas determinadas.

## NodePort

Aloca uma porta em todos os nodes de um cluster para acessar Pods. Também realiza tudo o que o ClusterIp realiza.

## LoadBalancer

Realiza tudo o que ClusterIp e NodePort fazer, porém oferece a possibilidade de utilizar o LoadBalancer do Cloud Provider. (Azure, Google Aws)
