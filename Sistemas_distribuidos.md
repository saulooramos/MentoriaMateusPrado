# SISTEMAS DISTRIBUIDOS - O porquê do DevOps

>O que é Sistema distribuido?

Antes de responder esta pergunta, precisamos entender o principal motivo da necessidade de termos um sistema distribuído.

## **Sistema Centralizado**

Sistema centralizado é o conceito que define como os sistemas "mais antigos" funcionam: 

![imagem de sistema centralizado](link da imagem)

>Mas qual o problema do sistema centralizado?

O principal desafio é manter de pé. Comumente, quando vários usuários acessam o sistema ao mesmo tempo, ele cai. Nesta configuração, por mais que tivéssemos mais de um servidor, em aplicações monolíticas, eles não se comunicam, ou seja, não compartilham dados: muitos problemas para os desenvolvedores e para operações.


### **Muitas empresas no Brasil ainda utilizam sistemas centralizados**

A primeira tentativa de organizar procedimentos que solucionassem os problemas foi a criação do **ITIL**, que nada mais é do que um modelo de gerenciamento com procedimentos padrão para infraestrutura de sistemas de TI.

## **Um novo modelo - Sistema distribuido**

![imagem de sistema distribuido](/imagens/sistema_distribuido.jpeg)

Agora, o número de elementos de infraestrutura (bancos de dados, cdn, load balancers, frontend, api gateway, backend, etc.) é flexível e atende justamente a demanda: utilizo quantos precisar e tudo está interconectado, compartilhando um caminho de ida e volta de dados.

![imagem do caminho da requisição](/imagens/fluxo_requisicao.jpeg)

Podemos ter agora uma infraestrutura que conte com (exemplo fictício):

- 2 instâncias de CDN;
- 1 instância de Load Balancer;
- 1 instância de Web Application Firewall;
- 10 instâncias de Frontend;
- 5 instâncias de API Gateway;
- 5 instâncias de Backend;
- 3 instâncias de banco de dados;

Ou seja, o sistema é distribuido de acordo com as suas necessidades, que são baseadas, principalmente, em métricas de performance e disponibilidade.

>Mas quais os desafios e riscos?

1. Operacional: Agora, com vários sistemas, muitas vezes as empresas têm mais serviços de infraestrutura do que da aplicação. Além disso, há necessidade de uma equipe preparada para lidar com mais sistemas e mantê-los de pé.

2. Network: Uma camada de rede mais complexa com muito mais configurações.

3. Deploy: Entrega mais complexa, já que agora a aplicação roda em várias máquinas.

4. Segurança: Segurança mais crítica com mais portas de entrada na aplicação.

5. Custo: Mais custo com time, treinamento e todos os tópicos mencionados acima.

## Engenheiro de Plataforma

O Platform Engineer (conhecido como Devops Engineer) veio para atender esta demanda de manter uma infraestrutura de alta complexidade operacional: Observabilidade, Deploy e Integração contínuos, Orquestração, Infraestrutura como código, ACLs, MFA, etc.

