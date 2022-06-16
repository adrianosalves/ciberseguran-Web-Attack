# Cibersegurança Forense Digital

**Ferramentas de Analise:**

https://app.any.run/

**Ataques para Aplicaçoes Web:**

https://www.acunetix.com/websitesecurity/web-application-attack/



Estudos OWASP:

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


