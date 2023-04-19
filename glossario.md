# Geral

SLA (Service Level Agreement) - Disponibilidade acordada em contrato

PoC (Proof of Concept) - Teste utilizado quando não se sabe a causa raíz

RCA (Root cause analisys) - Análise de causa raíz

Scaling out - Escalar horizontalmente

Scaling up - Escalar verticalmente

K8s - Kubernetes

&nbsp;

# DNS

DNS (Domain Name System) -  É um sistema de gerenciamento de nomes de domínio e endereços IP

TLD (Top Level Domain) - Dominio raiz (**.com**)

Domínio - Nome do site (**exemplo.com**)

Subdomínio - Ramificações do domínio principal (**www.**exemplo.com)

FQDN (Endpoint) - Full Qualified Domain Name (**www.exemplo.com**)

URI (Uniform Resource Identifier) - Identificador de recursos (www.exemplo.com/**recurso**)

TTL (Time to Live) - Tempo de vida do registro

Dig (Domain Information Groper) - Ferramenta de linha de comando para consulta de DNS

Record Type - Tipo de registro

* SOA (Start of Authority R*ecord) - Registro de início de autoridade

* NS (Name Server) - Indica qual servidor de DNS é autoritativo para o domínio em questão 

* A (Address) - The "A" stands for "address" and this is the most fundamental type of DNS record: it indicates the IP address of a given domain

* AAAA - An AAAA record maps a domain name to the IP address (Version 6) of the computer hosting the domain.

* CNAME (Canonical Name) - É um tipo de registro de recurso no Sistema de Nomes de Domínio que mapeia um nome de domínio para outro.

* TXT (Text Record) - Entrada de texto puro

* MX (Mail Exchange) - @ do dominio 

* PTR (Pointer Record) - Um registro de ponteiro fornece o nome de domínio associado a um endereço de IP.

* SPF (Sender Policy Framework) - Entrada de texto para definir o(s) IP(s) que estão auorizado a envir email com aquele domínio

&nbsp;

# OSI

OSI model (Open System Interconnection) - Modelo de interconexão de sistemas abertos

* Physical Layer (Camada Física) - Ambiente físico 

* Data Link Layer (Camada de dado) - Define o formato e converte  os dados em binários. Encriptação.

* Network Layer (Camada de rede) - Define o caminho dos dados

* Transport Layer (Camade de transporte) - Responsável por transimitr o dado. TCP/UDP são os protocolos mais utilziados

* Sesssion Layer (Layer de controle de sessão) - Mantém a conexão aberta e controla portas e sessões

* Presentation Layer (Camada de apresentação) - Responsável por converter os dados de binários para um formato legivel por humanos. Decriptação.

* Application Layer (Camada da aplicação) - Responsável por aplicar as regras de negócio

WAF (Web Application Firewall) - Firewall a nível de software

IP (Internet Protocol) - Protocolo de comunicação entre computadores

&nbsp;

# Protocolos de Comunicação e Segurança (HTTP, HTTPS, TCP, UDP, Stateful, Stateless)

TCP Transmission Control Protocol (Protocolo de Controle de Transmição) - Garantia de entrega e sequência dos pacotes

UDP User Datagram Protocol (Protocolo de Datagrama de Usuário) - Sem garantia de entrega dos pacotes

HTTP Hyper Text Transfer Protocol (Protocolo de Transferência de Hipertexto) - Protocolo de comunicação entre cliente e servidor

HTTPS Hypertext Transfer Protocol Secure (Protocolo Seguro de Transferência de Hipertexto) - Protocolo de segurança para HTTP

User Agent (Cliente) - Podendo ser humano ou uma aplicação

ESB Enterprise Service Bus (Barramento de Serviço Corporativo) - É um padrão pelo qual um componente de software centralizado realiza integrações a sistemas back-end

Query String (Cadeia de Caracteres de Consulta) - Parte da URL que contém os parâmetros de consulta (exemplo: ?id=1)

SOAP Simple Object Access Protocol (Protocolo Simples de Acesso a Objetos) - É um protocolo de comunicação entre aplicações que permite a troca de informações em formato XML entre aplicações que podem estar em diferentes plataformas e linguagens de programação

Rest Representational State Transfer (Transferência de Estado Representacional) - É um estilo de arquitetura de software para sistemas distribuídos baseado em transferência de estado, normalmente utilizado para criar Web Services

Stateful (Protocolo Com Estado) - É um protocolo de comunicação que mantém o estado de cada requisição, ou seja, cada requisição é dependente da requisição anterior

Stateless (Protocolo Sem Estado) - É um protocolo de comunicação que considera cada requisição como uma transação independente que não está relacionada a qualquer requisição anterior

Header (Cabeçalho) - Meta dados da requisição

Payload (Carga) - Dados da requisição

HTTP request methods [(Referência)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

 * [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) - O método GET solicita uma representação de um recurso específico. Requisições utilizando o método GET devem retornar apenas dados.

 * [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) - O método POST é usado para enviar uma entidade para o recurso especificado, frequentemente causando uma mudança no estado ou efeitos colaterais no servidor.

 * [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) - O método PUT substitui todas as atuais representações do recurso de destino pela carga de dados da requisição.

 * [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) - O método DELETE remove um recurso específico.

 * [HEAD](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) - O método HEAD solicita uma resposta idêntica àquela de uma requisição GET, mas sem o corpo da resposta.

 * [OPTIONS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS) - O método OPTIONS é usado para descrever as opções de comunicação com o recurso de destino.

 * [TRACE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE) - O método TRACE executa um teste de chamada loop-back junto ao caminho para o recurso de destino.

 * [PATCH](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) - O método PATCH é usado para aplicar modificações parciais em um recurso.

Status code [(Referência)](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html):

* [Informational responses (100 – 199)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses)

* [Successful responses (200 – 299)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#successful_responses)

* [Redirection messages (300 – 399)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#redirection_messages)

* [Client error responses (400 – 499)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses)

* [Server error responses (500 – 599)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#server_error_responses)

&nbsp;

# Load Balancer

Load Balancer - Distribui o tráfego entre os servidores

Round Robin - Distribui o tráfego de forma sequencial

Least Connections - Distribui o tráfego de forma proporcional ao número de conexões

IP Hash - Distribui o tráfego de forma proporcional ao IP do usuário

Stick Session - Mantém a sessão do usuário com o mesmo servidor

VIP (Virtual IP) - IP virtual que é atribuído ao Load Balancer e que é utilizado para distribuir o tráfego

Health Check - Verifica se o servidor está disponível

NGINX - Servidor de aplicação web e proxy reverso

# Home Lab

Home Lab - Ambiente de testes e estudos

AP (Access Point) - Dispositivo que permite a conexão de dispositivos sem fio a uma rede

Router - Dispositivo que permite a conexão de dispositivos com fio a uma rede

Switch - Dispositivo que permite a conexão de dispositivos com fio a uma rede

ISP (Internet Service Provider) - Provedor de serviços de internet

CORS (Cross-Origin Resource Sharing) - Permite que um site acesse recursos de outro site

Access Control - Controle de acesso

PoE (Power Over Ethernet) - Permite a transmissão de energia elétrica através de um cabo de rede

NAS (Network Attached Storage) - Armazenamento de dados em rede

Firewall - Dispositivo que permite a filtragem de pacotes de rede

Patch Panel - Dispositivo que permite a conexão de cabos de rede

Mesh Network - Tecnologia de rede sem fio que permite a conexão de dispositivos sem fio entre si sem a necessidade de um ponto de acesso central (exemplo: Wi-Fi Mesh)

VPN (Virtual Private Network) - Rede privada virtual

# CDN (Content Delivery Network)

CDN (Content Delivery Network) - Rede de distribuição de conteúdo

Edge Server - Servidor de borda

Origin Server - Servidor de origem

Cache - Cache

Cache Key - Chave de cache

Cache Policy - Política de cache

Cache Tag - Tag de cache

Cache Tag Header - Cabeçalho de tag de cache

Cache Tag Query String - Cadeia de caracteres de consulta de tag de cache

Cache Tag Cookie - Cookie de tag de cache

Cache Tag URI - URI de tag de cache

Cache Tag User Agent - Agente de usuário de tag de cache

ASSET (Application Server Side Includes) - Inclusão de conteúdo de um servidor de aplicação no lado do servidor

POP (Point of Presence) - Ponto de presença (localidade onde o CDN possui um servidor)

# Observability (Observabilidade)

Observability (Observabilidade) - Capacidade de observar o comportamento de um sistema

Observability Tools - Ferramentas de observabilidade

Metrics - Métricas

SLO (Service Level Objective) - Objetivo de nível de serviço

SLI (Service Level Indicator) - Indicador de nível de serviço

SLA (Service Level Agreement) - Acordo de nível de serviço

[Golden Signals](https://sre.google/sre-book/monitoring-distributed-systems/) - Sinais dourados são sinais que indicam o estado de saúde de um sistema (Latência, Tráfego, Erros, Utilização de recursos)

FinOps - Finanças operacionais (práticas que visam reduzir os custos operacionais)

# Object Storage

Object Storage - Armazenamento de objetos

File Storage - Armazenamento de arquivos

Structured File Storage - Armazenamento de arquivos estruturados

Block Storage - Armazenamento de blocos

Object - Objeto que pode ser um arquivo, um diretório ou um link simbólico

Bucket - Balde que é um container para armazenar objetos

Key - Chave que é o nome do objeto

Value - Valor que é o conteúdo do objeto

Metadata - Metadados que são informações sobre o objeto

SDS (Software Defined Storage) - Armazenamento definido por software

SDN (Software Defined Network) - Rede definida por software

NFS (Network File System) - Sistema de arquivos de rede