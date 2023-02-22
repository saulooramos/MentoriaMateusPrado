# DISPONIBILIDADE E ESCALABILIDADE

## Availability

>Qual a ideia? Como fazemos para manter tantos recursos disponíveis, considerando agora sistemas distribuídos?

A ideia é manter o sistema de pé para que o usuário consiga acessá-lo. Ao tratar de disponibilidade, precisamos definir conceitos à partir da necessidade, por isso devemos estabelecer um nível de disponibilidade aceitável a cada operação.

>Qual o nível de disponibilidade você quer manter? Já parou para pensar qual o nível de disponibilidade seu celular ofereceu esta semana?

Para responder à estas perguntas, levamos em consideração alguns aspectos como:

1. Em que período estamos avaliando?
2. Quantas horas neste período podemos ficar indisponíveis?

A partir destas duas questões podemos definir Service Level Agreement (SLA), que é um termo que consta no ITIL. É um termo de compromisso firmado como um item de contrato e está sujeito à lei. Neste caso, o sistema pode até estar lento, mas o importante é estar de pé.

Precisamos deixar claro que microsserviços não são altamente disponíveis por si só e além disso, existem aplicações monolíticas altamente disponíveis como por exemplo o ERP SAP. Ao mesmo tempo, mesmo utilizando Kubernetes (K8s), quando um POD cai e outro assume não resolvemos as questões de disponibilidade caso estejam sendo executados em uma mesma máquina.

![SAP ERP](SAP_ERP.jpeg)

Um SLA rigoroso traz consigo uma responsabilidade alta pois envolve a empresa toda e, em caso de falhas, há necessidade de reestabelecer o serviço o mais rápido possível, em muitos casos, pressionando as equipes envolvidas.

Um dos fatores a serem considerados ao se escolher um provedor de e-mails e CDN é o SLA.

SLA individual = (Período de avaliação - downtime)/ Período de avaliação

SLA sistema = multiplicação dos SLA individuais

Normalmente o menor SLA individual representa o SLA do sistema.

> Como definir um SLA?

Para se definir um SLA é necessário utilizar um histórico de tempo disponível como métrica.

## Scalability

>Qual a ideia?

É uma prática dentro de sistemas distribuídos para aumentar a disponibilidade. É praticado através de 03 formas:

1. Manualmente: Utilizar armazenamento de memória sólida (SSD), aumentar espaço livre de armazenamento, memória RAM, processamento, etc. Ou seja, melhorar a disponibilidade através de mudanças no hardware do servidor, acarretando pouca ou nenhuma vantagem.

2. Automático: Utilizar IaC para padronizar e escalar de acordo com métricas e triggers, ou seja, sem necessidade de interação humana. Possui muitas vantagens como recuperação de desastres com muito mais rapidez porém requer um tempo muito maior de investimento para construção do sistema.

3. Automatizado: Sistema automático mas com necessidade de interação humana para disparar as rotinas.

>Exemplo: Um sistema está fora do ar, o que fazer?

Primeiramente podemos adotar uma estratégia para analisar a causa raíz: Banco de dados parou? Disco crashou? Faltou memória? Ao responder estas perguntas temos um ponto chave de partida para tomada de decisão.

No caso deste exemplo, a causa raíz foi: Capacidade do equipamento não suportou a quantidade de usuários.

>Uma possível solução seria: colocar mais máquinas à disposição. Mas como?

Há basicamente duas formas de se fazer um sistema escalar: Horizontalmente (scaling out) ou Verticalmente (scaling up)

1. Horizontalmente: Aumento de processamento através da adição de mais unidades como containers, VM's, etc.
2. Verticalmente: Aumento de processamento através da adição de mais memória e processamento, na mesma unidade.

No caso do exemplo, utilizaríamos scaling out, ou seja, mais unidades à disposição. Porém, o custo e a arquitetura do sistema podem bloquear o scaling out, ou seja, não funciona em todos os casos!

> Um último conceito: Elasticidade

A elasticidade é a capacidade de um sistema poder aumentar ou diminuir a quantidade de unidades de acordo com a demanda, imprescindível para momentos como uma Black Friday.
