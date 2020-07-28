---
layout: post
title: PDI - Pentaho Data Integration
date: 2020-07-25 16:00:00
categories: pdi-pentaho integração-de-dados data-integration
image: "/assets/images/Pentaho-PDI.png" 
...
Uma das ferramentas mais utilizadas para ETL, integração de dados entre outros recursos destinados a área.
Vamos conhecer um pouco mais sobre o Pentaho? 

**O que é o Pentaho Data Integration ?** <br>
É um *Software open source* para inteligência de negócios (BI) baseado em Java, com foco em ETL (Extract, Transform, Load), mineração de dados e cubos OLAP (On-line Analytical Processing). Sua primeira versão foi lançada em 2004, onde no decorrer dos anos foi premiada como uma das melhores aplicações para inteligência empresarial.
Existe também outras ferramentas da Pentaho *Corporation*, por exemplo: Pentaho *Analysis* Services, Pentaho *Reporting*, Pentaho *Dashboard*.

 **Como funciona:**<br>
Basicamente o PDI funciona com Steps, onde cada um tem suas propriedades e características para exercer determinada função.
Os Steps são ligados por Hops - conectores, onde é seguido um fluxo para que seja executada uma determinada atividade. 
No simples exemplo abaixo, temos uma conexão a um banco de dados onde é executado um script SQL, inserido o resultado em um arquivo de texto .csv e enviado para um FTP (File Transfer Protocol), caso houver falha em algum Step, é enviado um e-mail para o analista responsável. 


[Step 01](https://melzilucas.github.io/assets/images/read-sql.png){:target="_blank" rel="noopener"} - leitura ao Banco de Dados e insere em um arquivo csv;

[Step 02](https://melzilucas.github.io/assets/images/put-ftp.png){:target="_blank" rel="noopener"} - captura o arquivo csv do Step anterior e envia para um FTP;

[Step 03](https://melzilucas.github.io/assets/images/job-full.png){:target="_blank" rel="noopener"} - Job completo chamando as transformações anteriores, em caso de falha é realizado envio de alerta via e-mail.

>Após todo o fluxo definido, para automatização do processo é possível agendar a execução dos Jobs através de uma Cron ou agendador de tarefas, dependendo do Sistema Operacional utilizado, sem necessidade da ferramenta está aberta.

Obs.: O tratamento dos dados pode ser realizado tanto no Script SQL como também utilizando os Steps do próprio Pentaho - remover espaços, replaces, concatenar, ordenar, agrupar, joins, case, entre outros. Se necessário, também é possível executar linguagens de programação, por exemplo: JavaScript.


 **Principais funções:** 
 * **Extração, transformação e carregamento de dados – ETL:** É possível se conectar a praticamente todos os SGBD's utilizados no mercado, API's, *WebServices*, FTP, leitura de arquivos em  local, entre outras inúmeras opções.<br> 
* **Organização – Data Warehouse:**  Da mesma maneira que é possível ler dados de diversas fontes, também pode-se popular os dados tratados para mais de um destino. <br>
* **Análise dimensional – Cubos OLAP:** Todo tratamento pode ser realizado dentro do PDI para evitar utilização de recursos na camada de visualização, logo o dado é entregue para ferramenta de BI conforme escopo definido.<br>
* **Monitoramento das informações:** É possível utilizar recursos do PDI como, relatórios, gráficos e dashboards. Uma característica altamente recomendada e muito utilizada em desenvolvimento, o versionamento das transformações ou de qualquer alteração no processo, com possibilidade de *Rollback.*


Fico à disposição para quem quiser bater um papo sobre a ferramenta, sugestões, ideias, críticas construtivas ou dúvidas. No meu [GitHub](https://github.com/melzilucas/Projects-ETL){:target="_blank" rel="noopener"} existe um repositório destinado aos projetos e estudo sobre a ferramenta.  
[Aqui](https://melzilucas.github.io/about.html){:target="_blank" rel="noopener"} você encontra meus contatos, valeu! :)