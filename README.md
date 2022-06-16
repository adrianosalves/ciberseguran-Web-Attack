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

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/Owasp-Top-10.png>


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

# Detectando ataques de injeção de SQL

**O que é injeção de SQL (SQLi)?***

SQL Injections são métodos de ataque críticos em que um aplicativo da Web inclui diretamente dados não higienizados fornecidos pelo usuário em consultas SQL.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/sql-injection.png>

As estruturas que usamos hoje em dia para desenvolver aplicativos da Web têm mecanismos preventivos para proteger contra ataques de SQL Injection. Mas ainda encontramos vulnerabilidades de SQL Injection porque às vezes são usadas consultas SQL brutas, às vezes o framework tem uma vulnerabilidade inata de SQL Injection ou o framework não é usado corretamente.

**Tipos de injeção de SQL**

Existem 3 tipos de SQL Injection. Estes são: 

- 1. SQLi In-band (SQLi Clássico) : Se uma consulta SQL é enviada e respondida no mesmo canal, chamamos esses SQLi In-band. É mais fácil para os invasores explorá-los em comparação com outras categorias SQLi.

- 2. SQLi inferencial (SQLi cego): consultas SQL que recebem uma resposta que não pode ser vista são chamadas de SQLi inferencial. Eles são chamados de Blind SQLi porque a resposta não pode ser vista.

- 3. SQLi fora de banda : Se a resposta a uma consulta SQL for comunicada por um canal diferente, esse tipo de SQLi é chamado de SQLi fora de banda. Por exemplo, se o invasor estiver recebendo respostas às suas consultas SQL pelo DNS, isso é chamado de SQLi fora de banda.

**Como funciona a injeção de SQL?**

Hoje, os aplicativos da Web padrão geralmente recebem dados de um usuário e usam esses dados para exibir conteúdo específico. A página de login é onde a maioria dos ataques de SQL Injection acontecem. Vamos examinar como as injeções de SQL funcionam por meio de um exemplo.

Geralmente, espera-se que um usuário insira seu nome de usuário e senha na página de login. Por outro lado, o aplicativo da web usará essas informações de nome de usuário e senha para criar uma consulta SQL como a abaixo:

SELECT * FROM users WHERE nome de usuário = ' USERNAME ' E senha = ' USER_PASSWORD '

O significado desta consulta SQL é “traga-me todas as informações sobre o usuário da tabela de usuários cujo nome é USERNAME e cuja senha é USER_PASSWORD ”. Se o aplicativo da web encontrar um usuário correspondente, ele autenticará o usuário, se não puder encontrar um usuário após a consulta ser realizada, o login não será bem-sucedido.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/Login-page.png>


Digamos que seu nome de usuário seja “ john ” e sua senha seja “ supersecretpassword ”. Quando você insere essas informações e clica no botão de login, a consulta SQL que você vê abaixo será consultada e você poderá entrar porque houve uma correspondência encontrada após a consulta SQL.

SELECT * FROM users WHERE username = ' john ' AND password = ' supersecretpassword '

Então, e se não usarmos esse sistema da maneira como ele foi projetado e colocarmos um apóstrofo (') na área de nome de usuário? A consulta SQL será como abaixo e o erro será excluído do banco de dados porque a consulta estava com defeito.

SELECT * FROM users WHERE username = ' john ' AND password = ' supersecretpassword '

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/SQL-Injection-login-page.png>

Um invasor ficaria feliz em receber uma mensagem de erro. O atacante pode manipular as informações na mensagem de erro para sua própria vantagem e também mostrar que ele está no caminho certo. E se o invasor inserir uma carga útil como a abaixo na área do nome de usuário?

' OU 1=1 – -

Quando o invasor enviar a carga útil, o aplicativo da Web executará a seguinte consulta SQL:

SELECT * FROM users WHERE username = '' OR 1=1 – - AND password = ' supersecretpassword '

No SQL, quaisquer caracteres que vierem depois de “-- -” serão percebidos como uma linha de comentário. Então, se olharmos para a consulta acima, as consultas que vêm depois de “-- -” não significam nada. Então, vamos remover essa parte para simplificar as coisas antes de continuarmos a examinar a consulta SQL.

SELECT * FROM users WHERE nome de usuário = '' OR 1=1

Então agora a consulta acima se parece com isso: “ se o nome de usuário estiver vazio ou 1=1 ”. Não é realmente importante se a área do nome de usuário é deixada vazia ou não, porque 1 é sempre igual a 1. É por isso que esta consulta sempre será verdadeira e provavelmente chamará a primeira listagem no banco de dados. O invasor poderá entrar com êxito no aplicativo da Web porque há uma correspondência.

Este exemplo é um ataque típico de injeção de SQL. É claro que os ataques de injeção de SQL não estão limitados a este exemplo, o invasor pode usar SQL para executar comandos no sistema com a ajuda de comandos SQL como  xp_cmdshell.

**Como os invasores aproveitam os ataques de injeção de SQL**

Para entender por que os ataques de injeção de SQL são tão importantes, vamos dar uma olhada no que um ataque de injeção de SQL pode causar.


- Bypass de autenticação

- Execução do comando

- Exfiltrando dados confidenciais

- Criando/excluindo/atualizando entradas de banco de dados

**Como evitar injeções de SQL**

Use um framework: claro que apenas usar um framework não será suficiente para evitar um ataque de SQL Injection. É de extrema importância usar o framework de acordo com a documentação.
Mantenha sua estrutura atualizada: mantenha seu aplicativo da Web seguro seguindo as atualizações de segurança relacionadas à estrutura que você usa.

Sempre limpe os dados recebidos de um usuário: nunca confie nos dados recebidos de um usuário. Além disso, não apenas limpe os dados do formulário, mas também faça o mesmo com outros dados (como cabeçalhos, URLs etc.)
Evite usar consultas SQL brutas: Você pode ter o hábito de escrever consultas SQL brutas, mas deve optar por fazer uso dos benefícios que um framework oferece e também deve fazer uso da segurança que ele oferece.


**Detectando ataques de injeção de SQL**

Discutimos o que os invasores podem fazer com um ataque de injeção de SQL na seção anterior. Cada um dos resultados de uma injeção de SQL mencionado acima pode causar grandes perdas para uma instituição, portanto, como analistas de SOC, devemos ser capazes de detectar esses ataques e tomar precauções contra eles.

Então, como podemos detectar ataques de injeção de SQL?

Há mais de uma resposta para esta pergunta. Estes são: 

- 1. **Ao examinar uma solicitação da Web, verifique todas as áreas que vêm do usuário:** Como os ataques de SQL Injection não se limitam às áreas do formulário, você também deve verificar os cabeçalhos de solicitação HTTP, como User-Agent.

- 2. **Procure por palavras-chave SQL:** procure por palavras como INSERT, SELECT, WHERE nos dados recebidos dos usuários.

- 3. **Verifique se há caracteres especiais:** procure apóstrofos ('), traços (-) ou parênteses que são usados ​​em SQL ou caracteres especiais que são frequentemente usados ​​em ataques SQL nos dados recebidos do usuário.

- 4. **Familiarize-se com cargas úteis de SQL Injection usadas com frequência:** embora as cargas úteis de SQL mudem de acordo com o aplicativo da Web, os invasores ainda usam algumas cargas comuns para verificar vulnerabilidades de SQL Injection. Se você estiver familiarizado com essas cargas úteis, poderá detectar facilmente cargas úteis de injeção de SQL. Você pode ver algumas cargas úteis de SQL Injection usadas com freqüência aqui .

**Detectando ferramentas automatizadas de injeção de SQL**

Os invasores usam muitos dispositivos automatizados para detectar vulnerabilidades de injeção de SQL. Um dos mais conhecidos é o Sqlmap. Vamos olhar para o quadro mais amplo em vez de focar em uma ferramenta específica.

Você pode usar os métodos listados abaixo para detectar dispositivos de injeção de SQL:

- 1. **Observe o User-Agent:** Dispositivos de navegador automatizados geralmente têm seus nomes e versões registrados. Você pode olhar para o User-Agent para detectar esses dispositivos automatizados.

 2. **Verifique a frequência das solicitações:** os dispositivos automatizados foram projetados para enviar uma quantidade estimada de muitas solicitações por segundo para poder testar as cargas úteis o mais rápido possível. Um usuário normal pode enviar 1 solicitação por segundo, portanto, você pode saber se as solicitações são feitas por um dispositivo automatizado ou não, observando o número de solicitações por segundo.

- 3. **Observe o conteúdo da carga útil:** os dispositivos automatizados geralmente gravam seus próprios nomes em suas cargas úteis. Por exemplo, uma carga útil de SQL Injection enviada por um dispositivo automatizado pode ter esta aparência:  sqlmap' OR 1=1

- 4. **A carga útil é complicada:** esse método de detecção nem sempre funciona, mas com base na minha experiência, posso dizer que os dispositivos automatizados enviam cargas úteis mais complicadas.

**Exemplo de detecção**

Temos logs de acesso de uma aplicação web que foi vítima de um ataque de SQL Injection. 

Você pode não ter ouvido o que é um log de acesso antes. Resumindo, esses são os logs de acesso do servidor web. Esses logs geralmente contêm o endereço IP de origem, a data, a URL solicitada, o método HTTP, o agente do usuário e o código de resposta HTTP. Esses logs são muito úteis em investigações.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/sql-injection-access-log.png>
(Logs de acesso de injeção de SQL)

Temos um log de acesso em mãos. Agora o que fazemos?

Em primeiro lugar, quando olhamos para as páginas que foram solicitadas, vemos que além de páginas como “info.php” que é bastante legível, também existem solicitações feitas para páginas que são complexas e possuem símbolos como %. Não podemos dizer que solicitações de páginas como essas sejam maliciosas, mas o fato de serem feitas repetidamente e muitas vezes é suspeito.

Em primeiro lugar, vamos falar sobre o que significam os símbolos %. Quando solicitamos uma página que contém caracteres especiais, essas solicitações não são transferidas diretamente para o servidor web. Em vez disso, nossos navegadores executam uma codificação de URL (Percent Encoding) dos caracteres especiais e substitui cada caractere especial por uma string de caracteres que começa com % e contém 2 caracteres hexadecimais. Portanto, as páginas que contêm o símbolo % acima são páginas que contêm caracteres especiais.

<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/URL-Encoding.png>

Agora que entendemos o significado dos símbolos %, vamos revisitar os logs de acesso. Quando olhamos para os pedidos, podemos ver facilmente que além dos símbolos % existem palavras legíveis como “UNION”, “SELECT”, “AND”, “CHR”. Por serem palavras específicas que pertencem ao SQL, podemos determinar que estamos frente a frente com um ataque de SQL Injection.

Para salvar nossos olhos, vamos tornar o exame um pouco mais fácil :) Você pode realizar uma pesquisa usando as palavras-chave “Online URL Decoder” para encontrar aplicativos da web que farão a decodificação de URL automaticamente para você. Para ler esses logs de acesso com mais facilidade, obterei ajuda desses aplicativos da web, fazendo isso não precisarei forçar meus olhos ou os seus.

Deixe-me acrescentar uma pequena nota. Não é aconselhável fazer upload de algo como logs de acesso que contenham informações críticas em um aplicativo da Web de terceiros. Os logs de acesso que enviei foram preparados especificamente para este treinamento, portanto, não há problema em fazê-lo. Mas você não deve cometer tais erros em sua vida profissional.


<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/Access-logs-with-URL-decoding.png>


Quando fazemos a decodificação da URL podemos ver com mais clareza que se trata de um ataque de SQL Injection. Então o que devemos fazer agora? Sim, confirmamos que é um ataque de injeção de SQL, mas vamos deixá-lo lá?

Claro que não. Agora vamos encontrar outras informações que pudermos nesses logs de acesso.


<img src=https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/sql-injection-access-logs-date.png>


Primeiro, vamos ver as datas de solicitação. Todas as cargas de SQL Injection foram enviadas em “19/Fev/2022 11:09:24”. Podemos ver que mais de 50 solicitações foram feitas em 1 segundo. O fato de tantos pedidos terem sido feitos em tão pouco tempo nos mostra que se trata de um ataque automatizado. Além disso, como mencionamos anteriormente, quando os invasores realizam testes manuais, eles optam por testar cargas fáceis primeiro. Mas quando olhamos para os logs de acesso vemos que os payloads são muito complicados. Isso mostra que o ataque pode muito bem ser automatizado.

Confirmamos que um ataque de injeção de SQL foi realizado e que foi realizado com um dispositivo automatizado. Assim podemos encerrar nossa análise, certo?

Falta mais um passo. Precisamos determinar se o ataque foi bem-sucedido ou não. Você pode determinar se um ataque de injeção de SQL foi bem-sucedido observando a resposta, mas em sua carreira profissional você quase nunca terá acesso à resposta. Podemos presumir que todas as respostas terão aproximadamente o mesmo tamanho porque o ataque é realizado na mesma página e sobre a variável “id”. Podemos estimar o sucesso do ataque observando o tamanho da resposta.

Infelizmente, o servidor web básico que foi desenvolvido para servir de exemplo não pode fornecer um tamanho de resposta confiável. Portanto, não podemos estimar se o ataque foi bem-sucedido olhando para este exemplo. Mas com servidores web configurados corretamente, podemos encontrar o tamanho da resposta nos logs de acesso. Você pode examinar essa área para determinar se há uma diferença notável nos tamanhos de resposta. Se houver uma diferença notável, você pode estimar que o ataque foi bem-sucedido. Mas, nessa situação, seria melhor encaminhar esse alerta para um analista de nível superior.

O que nós sabemos:

- 1. Houve um ataque de SQL Injection realizado no parâmetro “id” na página principal da aplicação web.

- 2. As solicitações vieram do endereço IP: 192.168.31.174.

- 3. Como houve mais de 50 solicitações por segundo, esse ataque foi executado por uma ferramenta automatizada de verificação de vulnerabilidades.

- 4. A natureza complexa das cargas úteis suporta a afirmação em # 3.

- 5. Não podemos determinar se a resposta foi bem-sucedida ou não porque não temos informações sobre o tamanho da resposta.

**Arquivos do curso**

Nome do arquivo: SQL Injection - Web Attacks.rar

Tamanho: 3 KB

Senha: acesso

Download: https://github.com/adrianosalves/ciberseguran-a-forense-digital/blob/main/SQL%20Injection%20-%20Web%20Attacks.rar

**Progresso das perguntas**

(Investigar arquivo 'SQL Injection - Web Attacks') Qual é o endereço IP do invasor que executou o ataque SQL Injection?

192.168.31.167
Resposta correta!


Os logs de acesso também contêm o endereço IP de origem

(Investigar arquivo 'SQL Injection - Web Attacks') O ataque de SQL Injection foi bem-sucedido? (Sim não)

sim
Resposta correta!


Procure tamanhos de resposta

(Investigar arquivo 'SQL Injection - Web Attacks') Qual é o tipo de ataque de SQL Injection? (Clássico, cego, fora de banda)

Clássico
Resposta correta!

-

(Investigar arquivo 'SQL Injection - Web Attacks') Em que data começou a fase de exploração do SQL Injection Attack? (Formato: MM/DD/AAAA HH:MM)

03/01/2022 08:35
Resposta correta!

Data exata em que a carga maliciosa foi enviada


**Pratique com alertas SOC**

🔗 115 - SOC165 - Possível carga útil de injeção de SQL detectada

SEVERITY	DATE	RULE NAME	EVENTID	TYPE	ACTION
High	Feb. 25, 2022, 11:34 a.m.	SOC165 - Possible SQL Injection Payload Detected	115	Web Attack	
 
EventID: 115
Event Time: Feb. 25, 2022, 11:34 a.m.
Rule: SOC165 - Possible SQL Injection Payload Detected
Level: Security Analyst
Hostname: WebServer1001
Destination IP Address: 172.16.17.18
Source IP Address: 167.99.169.17
HTTP Request Method: GET
Requested URL: https://172.16.17.18/search/?q=%22%20OR%201%20%3D%201%20--%20-
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64; rv:40.0) Gecko/20100101 Firefox/40.1
Alert Trigger Reason: Requested URL Contains OR 1 = 1
Device Action: Allowed
Show Hint 

