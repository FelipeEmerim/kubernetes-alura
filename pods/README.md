# Pods

Pods são a estrutura base do Kubernetes. Eles seriam equivalentes aos containers do Docker.

## Pods vs Containers

Os pods mantém muitos princípios dos containers, por exemplo, são efêmeros. A grande diferença é que um Pod é composto de um ou mais containers. Esses containers estão no mesmo host. Por isso não é possível expor a porta 80 duas vezes no mesmo Pod.

## Recursos

É uma boa prática definir os recursos utilizados pelos pods.
* Request: São os recursos consumidos "de cara" pelo seu pod. Ao ser criado, seu pod irá imediatamente possuir esses recursos reservados apenas para ele.
* Limit: São os recursos máximos que seu pod irá consumir
