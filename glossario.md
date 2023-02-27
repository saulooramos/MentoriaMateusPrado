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

# Dias 4 - OSI e TCP/IP

OSI model - 

* Physical Layer (Camada Física) - Ambiente físico 

* Data Link Layer (Camada de dado) - Define o formato e converte  os dados em binários. Encriptação.

* Network Layer (Camada de rede) - Define o caminho dos dados

* Transport Layer (Camade de transporte) - Responsável por transimitr o dado. TCP/UDP são os protocolos mais utilziados

* Sesssion Layer (Layer de controle de sessão) - Mantém a conexão aberta e controla portas e sessões

* Presentation Layer (Camada de apresentação) - Responsável por converter os dados de binários para um formato legivel por humanos. Decriptação.

* Application Layer (Camada da aplicação) - 

TCP - Garantia de entrega e sequência dos pacotes

UDP - Sem garantia de entrega dos pacotes

WAF (Web Application Firewall) - 