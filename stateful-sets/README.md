# Stateful sets

Stateful sets são como deployments, porém para aplicações que precisam manter o estado. Isto é feito através de persistent volumes.

*Mas já não é possível definir persistent volumes nos deployments?*
Sim, mas em um deployment TODAS as réplicas irão compartilhar o mesmo volume, enquanto no StatefulSet, cada réplica irá ter o seu próprio volume, respeitando o template de claim passado. O Pod mantém sua identidade, ou seja, se eu tenho 3 réplicas, terei 3 volumes, e caso uma réplica morra, ela será revivida com o mesmo ESTADO, utilizando o mesmo volume. Os volumes devem ser deletados manualmente se necessário. 
