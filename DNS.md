# Domain Name System

> O que é? Porque foi criado? Para que serve?

O DNS é um sistema distribuido, mais especificamente um database distribuido.

O endereço que digitamos no browser é chamado de domínio e é utilizado para que o usuário não precise colocar o IP do site que quer acessar. 

De maneira simples podemos dizer que endereço IP é um número num formato padrão que identifica o endereço de um computador.

O DNS:

1. Resolve o problema de ter que lembrar os números IP dos sites que queremos acessar;

2. Surge junto com a necessidade de conexão entre sistemas em diferentes localidades;

>### www.ventilador.com
Podemos dividir o DNS acima em 3 partes:

1. Top Level Domain (TLD): é a parte final do DNS, sob responsabilidade de uma empresa/orgão. O registro Br é responsável pelos TLD br e edu, por exemplo.

Exemplos de TLD:

com || br || edu || gov

2. Subdomínio: é a parte inicial do DNS. Conhecemos muito o subdomínio padrão www mas hoje ele está sendo cada vez menos utilizado.

3. Domínio: é a junção entre o TLD e o que vier depois do subdomínio, parte mais importante do DNS, considerando que é ele que vai dar o nome ao seu site.

Exemplos de dominios:

github.com || ventilador.com.br || linkedin.com

>Como pesquisar quem é o dono de um domínio?

Utilizando o comando -whois DOMINIO.TLD você obtém uma resposta com várias informaçoes, uma delas é o Name Server: o grande responsável por saber qual é o IP por trás do domínio. Caso a resposta contenha mais de um nserver, significa que uma estratégia de maior disponibilidade está sendo utilizada.

>Mas como isso tudo funciona por debaixo dos panos?

![imagem de FQDN](/imagens/FQDN.jpeg)

### Lembrando sempre que não há certo e errado se tratando de DNS!

## Dive Deep DNS

- Sempre teremos um IP ou então um outro DNS por trás de um DNS

>No browser, quando digitamos: www.ventilador.com.br e apertamos enter, como ele sabe o IP ou o DNS que está por trás?

O browser pergunta o IP para uma biblioteca local (libresolver) que avalia:

![imagem de fluxo libresolver](/imagens/Libresolver.jpeg)

>Mas afinal de contas, quem é o responsável pelo domínio?

Para descobrir é legal dar uma olhadinha através do comando nslookup DNS, que devolve uma resposta com o conteúdo: 

```
non-authoritative answer:
Name: DNS
Address: IP
```

Que siginifica: Segundo o servidor X, o IP do DNS que você solicitou é Y

Para que você consiga acessar via browser um DNS, é preciso que haja uma porta 80 ou 443 aberta no endereço de IP.

A porta padrão de DNS é a porta 53.

>Mas o que significa esse tal de non-authoritative?

Há dois tipos de servidores de DNS: autoritativos e não autoritativos. Os servidores autoritativos conhecem todos os DNS publicados na internet, já os não autoritativos servem como CDN, ou seja, armazenam informação de DNS cacheada para distribuir ao redor do mundo, aumentando disponibilidade e diminuindo latência.

![imagem servidores DNS](/imagens/servidores-dns.jpeg)

Um dos problemas que podem ocorrer relacionados ao DNS é o problema da propagação de informações. Pode ser que um usuário esteja acessando um DNS no browser que ainda não está com a informação mais recente, gerando conflitos.

Isso ocorre devido ao Time to live (TTL), que é o tempo para que uma informação seja verdadeira até atualizar. Definimos um TTL para o DNS e, a grosso modo, de acordo com a frequência de mudança no sistema.

TTL alto:

- demora mais para propagar a informação;
- frequência de cache nos nservers é menor;

TTL baixo:

- cache dos DNS com tempo de expiração menor;
- preciso fazer mais consultas nos não-autoritativos (maior latência);

Um caso onde o TTL é relevante é onde há failover, ou seja, troca da máquina principal por uma secundária, com um novo IP apontando para um mesmo DNS.

Sendo assim: TTL baixo para sistemas com alterações frequentes e TTL altos para sistemas com alterações menos frequentes.

Boa prática: TTL até no máximo 01hora para evitar maiores problemas.

## Record Types

>Já reparou que muitas coisas podem funcionar em um domínio?

Um e-mail, um site, uma aplicação, etc.

Se utilizarmos o comando dig DNS, teremos como resposta informações muito relevantes para realizarmos um troubleshoot de DNS. Uma delas é o tipo da entrada, ou record type, que é a forma como o DNS separa as coisas.

1. SOA: start of authority

Sempre existente em DNS público e contém informações sobre como funciona a parte de autoritativo: dono do domínio e taxa de refresh. É o primeiro passo para que o servidor autoritativo saiba informações sobre o DNS.

Não é recomendado mexer no SOA, quem determina é o provedor. A AWS por exemplo não permite alterações no SOA.

Troubleshoot: whois DNS - se funcionar, não é um SOA

2. NS: name server

Entrada de DNS que diz quais são os servidores que respondem pelo domínio (servidores autoritativos), responsáveis por propagar mudanças do domínio. É provido pelo provedor e registrado pelo orgão responsável pelo TLD.

3. A (IPV4) e AAAA (IPV6)

É a representação da relação entre um DNS e um IP. Record type A para IPV4 e AAAA para IPV6

4. CNAME: Canonical Name

Funciona como uma referência, um apelido, um alias para um endereço já existente do tipo A.

Exemplo:

```
   endereço           Record Type            IP
  ventilador.com           A             192.168.1.2
blog.ventilador.com      CNAME          ventilador.com
```

No caso de termos vários endereços tipo A para o mesmo IP, no dia em que o endereço do servidor mudar, precisamos mudar todos os IPs, um por um.

Para evitar este cenário, utilizamos um DNS CNAME.

Ao utilizar o comando dig www.github.com podemos visualizar que o DNS www.github.com é um CNAME do DNS github.com, do tipo A. Esta referência encontra-se na camada de DNS, ou seja, não é um redirect.

![imagem github CNAME](/imagens/github-cname.jpeg)

>Como funciona no caso de um Load Balancer?

O IP do DNS é o IP do Load balancer. Quando você contrata um Load Balancer, por exemplo, na AWS, você recebe um FQDN no formato:

`abcd1234.lb.aws`

Sendo assim, uma boa prática é criar um DNS do tipo CNAME atrelado à ele:

```
   endereço           Record Type            IP
ventilador.com          CNAME          abcd1234.lb.aws
abcd1234.lb.aws           A             192.168.130.2
```
5. TXT: texto puro

É utilizado na maior parte das vezes com o token que o servidor de e-mails enviou para o responsável pelo DNS para validação como conteúdo.

Recomenda-se criar uma caixa de e-mail nos seguintes domínios:

@webmaster, @webmail, @root, @admin, @meudominio para validação através de email.

Outro use case do TXT é para certificados digitais como o do serviço acm da AWS.

SPF (sender policy framework): utilizado para dizer ao domínio quem são os servidores autorizados a enviar e-mail através do domínio. Funciona como controle de SPAM. Vai migrar um servidor? Configure o SPF! A maior parte dos SPF são entradas TXT.

6. MX: @ do domínio (endereço de email)

Funciona como domínio para o endereço de email do DNS

7. PTR

Entrada para consulta reversa no DNS, válido somente para entradas do tipo A. Dado um IP, qual é o seu nome?

Possui somente uma função: ajudar em troubleshooting de casos específicos.

>Alguns pontos a serem considerados

1. Se você possui mais de um IP do tipo A para o mesmo DNS, o DNS faz um rounding robbing e funciona como um load balancer, enviando requisiçoes cada hora para um endereço IP.

2. Monitoramento de log de status code de páginas + monitoramento de conteúdo pode ajudar a evitar páginas em branco sem motivo aparente.

3. Redirects devem ser feitos para uma URL e não para um IP.
