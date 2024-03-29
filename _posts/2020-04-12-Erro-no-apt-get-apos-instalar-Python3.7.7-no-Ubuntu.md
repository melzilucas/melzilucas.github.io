---
title:  Erro no apt-get após instalar Python 3.7.7 no Ubuntu
categories:
  - ubuntu
  - python

tags:
image: "/assets/images/01.png"
---


<p>Após intalar a versão 3.7.7 do Python no Ubuntu 18.04, tive problemas com o gerenciador de pacotes apt-get e também acusava um erro referente às atualizações do sistema, na barra superior: <b>problem occurred when checking for the updates.</b></p>

Buscando soluções em fóruns e comunidade, encontrei diversos tópicos que indicavam retornar para versão anteriores do Python, ou até mesmo remove-lô. Outro ponto bastante curioso, o terminal padrão do Ubuntu, conhecido como gnome terminal, não estava funcionando. Neste caso, ao atualizar o gerenciador de pacotes com o comando: 
~~~python
$ sudo apt-get update
~~~
Retornava o seguinte erro:

<p><img class="image-post" src="/assets/images/01.png"></p>

<p>O sistema de empacotamento apt possui um conjunto de chaves confiáveis ​​que determinam se um pacote pode ser autenticado e, portanto, confiável para ser instalado no sistema. Às vezes, o sistema não possui todas as chaves necessárias e corre para esse problema. Felizmente, há uma solução rápida.</p>
<p>Obervando o erro na imagem acima, podemos identificar a seguinte chave faltante: <b>4773BD5E130D1D45</b></p>

Para adicionar a chave, execute o comando:<br> 
~~~python 
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys [chave] 
~~~

<p><img class="image-post" src="/assets/images/02.png"></p>
Após adicionar a chave, rodei o comando para atualizar o gerenciador de pacotes:
~~~python
$ sudo apt-get update
~~~


<p><img class="image-post" src="/assets/images/03.png"><br>
<br>
Conforme imagem acima, não ocorreu mais nenhum erro durante a atualização e no meu caso, o terminal gnome e as atualizações do sistema, voltaram a funcionar normalmente.
