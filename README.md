# Cibersegurança

**Introdução** 

Preparamos o treinamento Web Attacks 101 para fornecer uma melhor compreensão dos ataques cibernéticos (dos quais 75% são aplicativos baseados na web) e como responder a esses ataques.

**O que são Ataques na Web?**

Aplicativos da Web são aplicativos que fornecem serviços para usuários por meio de uma interface de navegador. Hoje, os aplicativos da Web representam uma grande parte do uso da Internet. Sites como Google, Facebook e YouTube (excluindo os aplicativos móveis) são na verdade aplicativos da web.

Como os aplicativos da Web são uma interface na Internet para muitas organizações, os invasores podem explorar esses aplicativos e se infiltrar nos dispositivos, capturar dados pessoais ou causar falhas no serviço, causando sérios danos financeiros. 

Um estudo da Acunetix determinou que 75% de todos os ataques cibernéticos realizados foram no nível de aplicativos da web.

Abaixo, você encontrará alguns métodos de ataque usados ​​para se infiltrar em aplicativos da web. Abordaremos esses métodos em nosso curso “Ataques na Web 101”; explicaremos quais são esses métodos, como e por que os invasores os usam e como podemos detectar essas atividades.


Injeção SQL

Script entre sites

Injeção de Comando

IDOR

RFI e LFI

Upload de arquivo (Web Shell)

Qual habilidade você irá adquirir ao final do curso?
Você obterá conhecimento sobre vulnerabilidades da Web, como SQL Injection, Command Injection, IDOR; conhecimento sobre para que finalidade os hackers usam esses métodos e ganham as habilidades para identificar esses métodos de ataque.

Referências

[1] https://www.acunetix.com/websitesecurity/web-application-attack/

**Por que detectar ataques na Web é importante** 

Quando você olhar para a vida diária do Joe Médio, verá que ele usa muitos aplicativos da web ao longo do dia. Há os que visitam o Spotify para ouvir música, os que visitam o YouTube para ver vídeos ou os que usam as redes sociais.

Não é surpresa que os invasores escolham aplicativos da Web como um gateway para seus ataques porque todas as instituições têm aplicativos da Web que contêm principalmente dados críticos e porque os aplicativos modernos são altamente complicados e têm vários vetores de ataque. Um estudo realizado pela Acunetix reembolsa essa ideia.

“””Pesquisas recentes mostram que 75% dos ataques cibernéticos são feitos no nível do aplicativo da web.””” [1]

Se examinarmos a anatomia de um ataque, veremos que o melhor cenário é prevenir o ataque em sua primeira fase. Por esta razão, existem várias precauções de segurança que visam prevenir e detectar aplicações web (regras WAF, IPS, SIEM…).

É crucial que um analista de SOC detecte esses ataques baseados em aplicativos da Web que são a preferência dos invasores e tome precauções contra eles.

Referência [1]        https://www.acunetix.com/websitesecurity/web-application-attack/


**OWASP**

O Open Web Application Security Project (OWASP) é uma fundação sem fins lucrativos que trabalha para melhorar a segurança do software.[1]

Não há dúvidas de que o OWASP é um dos melhores recursos para obter informações sobre segurança de aplicações web.

**Top 10 OWASP**

OWASP publica uma lista de 10 vulnerabilidades de aplicativos da Web que possuem os riscos de segurança mais críticos a cada dois anos. No momento da redação deste artigo, a última publicação foi em 2021.


A lista OWASP publicada em 2021 contém estes riscos críticos de segurança:


Controle de acesso quebrado

Falhas criptográficas

Injeção

Design inseguro

Configuração incorreta de segurança

Componentes vulneráveis ​​e desatualizados

Falhas de Identificação e Autenticação

Falhas de integridade de software e dados

Registro de segurança e falhas de monitoramento

Falsificação de solicitação do lado do servidor (SSRF)

Você pode ler a publicação OWASP que contém os riscos de segurança mais críticos aqui .

Referências

[1] https://owasp.org/


**Progresso das perguntas**

Em que área o OWASP está focado?
A) Aplicativos da Web
B) Gerenciamento de servidor
C) Segurança sem fio

A
Resposta correta!
Qual é o nome da ferramenta que o OWASP preparou para ajudar a verificar vulnerabilidades de segurança em aplicativos da web?

ZAP
Resposta correta!


Você pode olhar para Projetos OWASP. Digite o nome abreviado da ferramenta. (Formato: XXX)

Qual é o nome do projeto de aplicação web vulnerável que o OWASP escreveu com o Node.js para os pesquisadores de segurança se aprimorarem? (Formato: xxx_xxx)

JUICE_SHOP
Resposta correta!


Navegue pelos projetos no menu da página inicial do OWASP. Algo como "juice_XXXX"

O que mostra a lista Top 10 da OWASP, publicada a cada poucos anos?
A) Riscos de segurança mais críticos para aplicativos móveis
B) Riscos de segurança mais críticos para aplicativos da Web
C) Vulnerabilidades de aplicativos da Web mais encontradas
D) Vulnerabilidades de aplicativos móveis mais encontradas

B
Resposta correta!


https://owasp.org/www-project-top-ten/

**Como funcionam os aplicativos da Web**

Para detectar uma anomalia, devemos primeiro entender como a tecnologia funciona. Os aplicativos utilizam determinados protocolos para se comunicar com precisão uns com os outros. Os aplicativos da Web se comunicam por meio do protocolo HTTP (Hyper-Text Transfer Protocol). Vamos ver como o protocolo HTTP funciona.

Para começar, é importante saber que o protocolo HTTP está na 7ª camada do modelo OSI. Isso significa que protocolos como Ethernet, IP, TCP e SSL são usados ​​antes do protocolo HTTP.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/HTTP-Protocol-TCP-IP-Model-OSI-Model.png>


A comunicação HTTP ocorre entre o servidor e o cliente. Primeiro, o cliente solicita um recurso específico do servidor. O servidor recebe a solicitação HTTP e envia de volta uma (Resposta HTTP) ao cliente após passá-la por determinados controles e processos. O dispositivo do cliente recebe a resposta e exibe o recurso solicitado em um formato apropriado.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/HTTP-Request-and-HTTP-Response.png>


Vamos examinar as solicitações HTTP e as respostas HTTP com mais detalhes.

**Solicitações HTTP** 

Uma solicitação HTTP é usada para recuperar um determinado recurso de um servidor web. Este recurso pode ser um arquivo HTML, vídeo ou dados json etc. O trabalho do servidor web é processar a resposta recebida e apresentá-la ao usuário. 

Existe um formato HTTP padrão e todas as solicitações devem obedecer a esse formato para que os servidores da Web possam entender a solicitação. Se a solicitação for enviada em um formato diferente, o servidor da Web não a entenderá e enviará um erro ao usuário ou o servidor da Web pode não ser capaz de fornecer o serviço (que é outro tipo de ataque).

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/HTTP-Request.png>

Uma linha de solicitação HTTP consiste em uma linha de solicitação, cabeçalhos de solicitação e um corpo de mensagem de solicitação. Uma linha de solicitação consiste no método HTTP e no recurso solicitado do servidor web. O cabeçalho da solicitação contém determinados cabeçalhos que o servidor processará. O corpo da mensagem de solicitação contém dados que devem ser enviados ao servidor.

Na imagem acima você vê um exemplo de uma solicitação HTTP. Vamos examinar essa solicitação HTTP linha por linha.

- 1. O método GET informa que o recurso “/” é solicitado do servidor. Como não há nome, um símbolo como “/” significa que a página principal do servidor web é solicitada.
- 2. Hoje em dia existem aplicativos web que pertencem a mais de um domínio encontrados em um único servidor web, então os navegadores usam o cabeçalho “Host” para descrever a qual domínio o recurso solicitado pertence.
- 3. Quando um aplicativo da web deseja armazenar informações no dispositivo do cliente, ele as armazena em um cabeçalho “Cookie”. Os cookies são geralmente usados ​​para armazenar informações de sessão. Portanto, você não precisa digitar novamente seu nome de usuário e senha ao visitar um aplicativo da Web que exija login. 
- 4. O cabeçalho “Upgrade-Insecure-Requests” é usado para indicar que o cliente deseja se comunicar com criptografia (SSL).
- 5. Há informações sobre o navegador e o sistema operacional do cliente no cabeçalho "User-Agent'". Os servidores da Web usam essas informações para enviar respostas HTTP específicas ao cliente. Você pode encontrar alguns scanners de vulnerabilidade automatizados olhando sob este cabeçalho.
- 6. O tipo de dados solicitados encontra-se no cabeçalho “Aceitar”.
- 7. O tipo de codificação que o cliente entende é encontrado no cabeçalho “Accept-Encoding”. Normalmente, você pode encontrar nomes de algoritmos de compactação nesse cabeçalho.
- 8. Sob o cabeçalho “Accept-Language” você pode encontrar as informações de idioma do cliente. O servidor web usa essas informações para exibir o conteúdo preparado no idioma do cliente.
- 9. O cabeçalho “Connection” mostra como será feita a conexão HTTP. Se houver algum dado como “fechar” encontrado aqui, significa que a conexão TCP será fechada após o recebimento da resposta HTTP. Se você vir "Keep-alive", isso significa que a conexão será continuada.
- 10. Uma linha vazia é colocada entre o cabeçalho da solicitação HTTP e o corpo da mensagem da solicitação HTTP para fazer uma partição.
- 11. Outros dados destinados a serem enviados para o aplicativo da Web são encontrados no Corpo da mensagem de solicitação. Se o método HTTP POST for usado, os parâmetros POST poderão ser encontrados aqui.

#Respostas HTTP

Uma vez que o servidor web recebe uma solicitação HTTP, ele executa os controles e processos necessários e, em seguida, envia o recurso solicitado ao cliente. Não há um processo uniforme aqui porque existem inúmeras tecnologias e designs envolvidos. O servidor pode extrair dados do banco de dados de acordo com o recurso solicitado ou pode processar de acordo com os dados recebidos. Mas a Mensagem de Resposta HTTP deve chegar ao cliente após todo o processamento.

Uma mensagem de resposta HTTP contém uma linha de status, cabeçalhos de resposta e um corpo de resposta. A Linha de Status contém o código de status (como 200: OK) e as informações do protocolo HTTP. Existem cabeçalhos usados ​​para diversas finalidades no Cabeçalho de Resposta. Os dados relacionados ao recurso solicitado são encontrados no Corpo de Resposta.

Se uma página da web foi solicitada, geralmente haverá códigos HTML no corpo da resposta. Quando o cliente recebe o código HTML, o navegador da Web processa o código HTML e exibe a página da Web.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/HTTP-Response.png>


Você pode ver uma solicitação de resposta HTTP na imagem acima. Vamos examinar uma solicitação de resposta HTTP com base nessa imagem.




Linha de status

Há informações sobre a versão HTTP e o código de status de resposta HTTP na Linha de Status. O código de status de resposta HTTP é usado para descrever o status da solicitação. Existem muitos códigos de status de resposta HTTP, mas eles podem ser resumidos assim:

●      100-199 : respostas informativas

●      200-299 : respostas bem-sucedidas

●      300-399 : mensagens de redirecionamento

●      400-499 : respostas de erro do cliente

●      500-599 : respostas de erro do servidor




Cabeçalhos de resposta

Aqui estão alguns cabeçalhos de resposta HTTP que você pode encontrar com frequência:

●      Data : A hora exata em que o servidor enviou a resposta HTTP ao cliente.

●      Conexão : Indica como a conexão será tratada, assim como no cabeçalho HTTP Request. 

●      Servidor : Informações sobre o sistema operacional do servidor e a versão do servidor web. 

●      Last-Modified : Informações sobre quando o recurso solicitado foi alterado. Este cabeçalho é usado para o mecanismo de cache.

●      Content-Type : O tipo de dados que é enviado. 

●      Content-Length : O tamanho dos dados enviados. 



Corpo de resposta

O Corpo de Resposta HTTP contém o recurso que foi enviado pelo servidor e solicitado pelo cliente. 


#Progresso das perguntas

Qual cabeçalho de solicitação HTTP contém informações do navegador e do sistema operacional?

User-Agent
Resposta correta!


Você pode usar as Ferramentas do desenvolvedor (F12) para examinar os cabeçalhos de solicitação.

Qual é o código de status de resposta HTTP que indica que a solicitação foi bem-sucedida?

200
Resposta correta!


OK

Qual método de solicitação HTTP garante que os parâmetros enviados não apareçam na URL de solicitação?

POST
Resposta correta!


RECEBER ou POSTAR

Qual cabeçalho de solicitação HTTP contém tokens de sessão?

Cookie
Resposta correta!


Você pode usar as Ferramentas do desenvolvedor (F12) para examinar seus cabeçalhos de solicitação.

Em qual camada do modelo OSI o HTTP é um protocolo?

Application
Resposta correta!


- Talvez você tenha perdido a informação na lição?
- A resposta não é um número, o nome da camada

