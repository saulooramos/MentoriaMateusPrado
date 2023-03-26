# Modelo OSI /OSI Model

![MODELO OSI](/imagens/modelo-osi.jpg)

> O que é? Para que serve?

Open Systems Interconnection: é um modelo de conexão entre sistemas. Serve para dizer como sistemas de computadores podem conectar entre si.

> Como um computador pode ser conectado à outro?

1. Equipamento físico: placa de rede + cabo crossover
2. Sistema Operacional com capacidade de receber e enviar informações

![CONEXÃO USUÁRIOS](/imagens/conexao-usuarios.jpeg)

## OSI 101

O modelo de camada OSI divide-se em 7 camadas, cada uma com sua responsabilidade.

1. Physical Layer: Cabos, fibra, onde se conectam os dispositivos, roteadores, hacks. A responsabilidade da camada física é, por exemplo, de quem trabalha em datacenters.

2. Data Link Layer: É onde os dados começam a ser "montados", transformando a mensagem em linguagem de máquina. É na Data Layer que há a definição do formato que o dado, que vai sair, vai chegar em seu destino. 

3. Network Layer: Reponsável por decidir por onde o dado vai passar. São os "Correios" da conexão. Define-se na network layer o caminho e a rota a se percorrer.

4. Transport Layer: Responsável por transmitir os dados utilizando algum protocolo de transmissão. Define a partir de qual protocolo o dado será trafegado, é TCP? UDP? É na transport layer que acontece a retransmissão de um pacote.

> Qual a principal diferença entre conexão TCP e UDP?

Na conexão TCP há garantia de entrega de requisição e resposta, ou seja, enviamos uma informação e ela deve retornar de alguma forma. Na conexão UDP não há garantia de resposta. Atualmente a internet utiliza muito mais o protocopo TCP, mas um benefício de se utilizar conexão UDP é basicamente performance, por economizar o retorno, a resposta da requisição (como tudo na computação, cada caso requer análise para entender qual o melhor protocolo a se utilizar).

5. Session Layer: Onde há necessidade de retornar alguma informação, como uma confirmação de que a mensagem enviada foi entregue, é necessário estabelecer uma conexão e mantê-la. É nesta camada que funciona o controle de portas e sessões e onde consegue-se identificar se há perdas de pacotes, por exemplo.

![SESSION LAYER](/imagens/session-layer.jpeg)

6. Presentation Layer: É ela que formata o dado (faz como se fosse o contrário da data link layer) para apresentar ao usuário e é onde ocorre criptografia de dados.

![PRESENTATION LAYER PDF](/imagens/presentation-layer-pdf.jpeg)

7. Application Layer: É a camada da aplicação em si. Pode conter WAF (URL, URI, path, rota, horário, geolocalização)

> Mas e aí? Como é utilizado no dia a dia?

Poderíamos resumir OSI em apenas duas camadas, mas a internet hoje trabalha com basicamente 4 camadas, o modelo de referência TCP/IP:

![OSI TCPIP](/imagens/osi-tcpip.jpg)

" É preciso saber onde queremos chegar para saber também como pedir ajuda, saber um pouco sobre o modelo OSI é sua responsabilidade" - Mateus Prado.
