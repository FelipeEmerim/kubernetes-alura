# Ingress

Ingress define uma forma de acessar serviços de fora do cluster. Ele seria o equivalente a um gateway.

## Nginx ingress

Neste projeto utilizamos o Nginx como ingress. Dessa forma é possível redirecionar requisições simples para o serviço desejado, possibilitando, por exemplo que requisições para o domínio service-1.com sejam encaminhadas para o serviço 1 enquanto requisições para o domínio service-2.com sejam encaminhadas para o serviço 2. Ainda é possível encaminhar requisições de services.com/service-1 para o serviço 1 e requisições de services.com/service-2 para o serviço 2, utilizando o mesmo domínio. Útil na arquitetura de microserviços, quando um produto possui mais de um serviço de borda.
