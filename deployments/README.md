# Deployments

Deployment é um recurso do kubernetes para gerenciar versões e o estado de pods, além de manter réplicas de pods. Faz tudo o que um replicaSet faz, but with lasers.

## Rollout

Deployments trabalham em rollouts. Cada rollout seria uma versão da aplicação, os rollouts são aplicados dinamicamente, dessa forma, não há downtime. Ele derruba réplica 1 de um pod, cria nova réplica do pod com versão nova, derruba réplica 2 , cria nova réplica do pod com nova versão. É possível também dar rollback em rollouts para uma versão anterior e ver o histórico de revisões.

## Réplicas

è possível definir réplicar e aplicar scalling em deployments. Na sua forma mais básica um deployment garante que sempre haverão X réplicas disponíveis. Caso um pod morra, outro é imediatamente criado em seu lugar.

## Probes

* startup-probe: Tempo para o container realizar seus processos necessários de inicalização como, por exemplo, buildar código, configuração inicial. Enquanto startup-probe não tiver sucesso, outras checagens não rodam. Necessário para aplicações mais legadas, utilizado no projeto apenas para exemplo
* liveness-probe: Indica que o container está 'vivo'. Um container que falha essa checagem será descartado e outro será iniciado em seu lugar.
* readiness-probe: Indica que o container está 'pronto para o combate'. Um container que não está pronto para o combate não é descartado, porém requisições não são encaminhadas para ele. Em um rollout, enquanto o novo container não estiver pronto, o container antigo não será descartado. Esse probe deve ser implementado com mais atenção do que o liveness, pois deve garantir que a aplicação rodando tem tudo o que ela precisa ter para funcionar. Nesse projeto mantemos igual por simplicidade

