# Deployments

Deployment é um recurso do kubernetes para gerenciar versões e o estado de pods, além de manter réplicas de pods. Faz tudo o que um replicaSet faz, but with lasers.

## Rollout

Deployments trabalham em rollouts. Cada rollout seria uma versão da aplicação, os rollouts são aplicados dinamicamente, dessa forma, não há downtime. Ele derruba réplica 1 de um pod, cria nova réplica do pod com versão nova, derruba réplica 2 , cria nova réplica do pod com nova versão. É possível também dar rollback em rollouts para uma versão anterior e ver o histórico de revisões.

## Réplicas

è possível definir réplicar e aplicar scalling em deployments. Na sua forma mais básica um deployment garante que sempre haverão X réplicas disponíveis. Caso um pod morra, outro é imediatamente criado em seu lugar.
