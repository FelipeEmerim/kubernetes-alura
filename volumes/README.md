# Volumes no kubernetes

Volumes no kubernetes funcionam de forma bem similar ao Docker. Eles armazenam dados de forma bidirecional.

## Volumes normais

Volumes "normais" são vinculados ao ciclo de vida de um pod e existem enquanto o pod existir. Caso o pod seja apagado, o volume também é. o Pod `volume-pod.yaml` utiliza um volume normal. Utilizar o mesmo volume significa que ao publicar uma alteração, todos os outros consumidores daquele volume verão sua alteração e vice-versa

## Volumes persistentes

Volumes persistentes são volumes que existem independente do Pod. Eles são reservados através de claims. Uma claim é uma forma de dizer "Preciso de um volume com X características", o kubernetes então procura os volumes disponíveis até encontrar um que atenda essa claim. O mapeamento entre volumes e claims é um para 1. Ou seja, utilizar a mesma claim em múltiplos Pods resulta em um volume compartilhado. (Necessária claim do tipo ReadWriteMany). O pod `db-noticias.yaml` possui um volume persistente.

## Volumes dinâmicos e Storage classes

StorageClasses é uma forma de definir tipos de volumes. Podemos ter uma classe por exemplo de volumes rápidos: SSD e outra classe de volumes lentos HDD. Elas se destacam quando utilizamos o campo provisioner, podendo assim criar volumes dinamicamente. Isso significa que ao passar uma StorageClass para uma claim, o provisioner pode gerar o volume em tempo real, sem a necessidade de criação prévia dele. É possível utilizar o minikube para gerar volumes dinâmicos. `minikube-st-class.yaml`, `minikube-pv-claim.yaml` e `volume-pod.yaml`.
