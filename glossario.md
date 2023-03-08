# Dia 1

SLA (Service Level Agreement) - Disponibilidade acordada em contrato

PoC (Proof of Concept) - Teste utilizado quando não se sabe a causa raíz

RCA (Root cause analisys) - Análise de causa raíz

Scaling out - Escalar horizontalmente

Scaling up - Escalar verticalmente

K8s - Kubernetes

# Dias 2 e 3 - DNS

TLD (Top Level Domain) - Dominio raiz (**.com**)

Domínio - (**exemplo**.com)

Subdomínio - Ramificações do domínio principal (**www.**exemplo.com)

FQDN (Endpoint) - Full Qualified Domain Name (**www.exemplo.com**)

URI (Uniform Resource Identifier) - Identificador de recursos (www.exemplo.com/**recurso**)

TTL (Time to Live) 

Dig (Domain Information Groper)

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

# Dia 4 - OSI e TCP/IP

OSI model - 

* Physical Layer (Camada Física) - Ambiente físico 

* Data Link Layer (Camada de dado) - Define o formato e converte  os dados em binários. Encriptação.

* Network Layer (Camada de rede) - Define o caminho dos dados

* Transport Layer (Camade de transporte) - Responsável por transimitr o dado. TCP/UDP são os protocolos mais utilziados

* Sesssion Layer (Layer de controle de sessão) - Mantém a conexão aberta e controla portas e sessões

* Presentation Layer (Camada de apresentação) - Responsável por converter os dados de binários para um formato legivel por humanos. Decriptação.

* Application Layer (Camada da aplicação) - 

WAF (Web Application Firewall) - Firewall a nível de software

# Dia 5 e 6 - HTTP

TCP Transmission Control Protocol (Protocolo de Controle de Transmição) - Garantia de entrega e sequência dos pacotes

UDP User Datagram Protocol (Protocolo de Datagrama de Usuário) - Sem garantia de entrega dos pacotes

HTTP Hyper Text Transfer Protocol (Protocolo de Transferência de Hipertexto) - 

HTTPS Hypertext Transfer Protocol Secure (Protocolo Seguro de Transferência de Hipertexto) - 

User Agent (Cliente) - Podendo ser humano ou uma aplicação

ESB Enterprise Service Bus (Barramento de Serviço Corporativo) - É um padrão pelo qual um componente de software centralizado realiza integrações a sistemas back-end

Query String (Cadeia de Caracteres de Consulta) - 

SOAP Simple Object Access Protocol (Protocolo Simples de Acesso a Objetos) - 

Rest Representational State Transfer (Transferência de Estado Representacional) - 

Stateless (Protocolo Sem Estado) - É um protocolo de comunicação que considera cada requisição como uma transação independente que não está relacionada a qualquer requisição anterior

Header (Cabeçalho) - Meta dado

Payload (Carga) - 

HTTP request methods [(Referência)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

 * [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET)

 * [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)

 * [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT)

 * [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE)

 * [HEAD](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD)

 * [OPTIONS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS)

 * [TRACE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE)

 * [PATCH](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH)

Status code [(Referência)](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html):

* [Informational responses (100 – 199)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses)

* [Successful responses (200 – 299)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#successful_responses)

* [Redirection messages (300 – 399)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#redirection_messages)

* [Client error responses (400 – 499)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses)

* [Server error responses (500 – 599)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#server_error_responses)