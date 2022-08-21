---
title: Breve introdução sobre Apache NiFi 
categories:
  - Apache Ni-fi
  - integração-de-dados
  - data-integration

tags:
image: "/assets/images/apachenifi.png" 
---

O Apache NiFi é um *software* de código aberto para automatização e gerenciamento de fluxos de dados entre sistemas. É um sistema poderoso e altamente confiável para processamento e distribuição dos dados. Possui uma interface para criar, monitorar e controlar fluxos de dados.

Nos permite criar lógicas complexas de integração, contendo fluxos de erros, retentativas, gerenciamento de filas em *realtime*, priorização dinâmica em tempo de execução, contemplando regra de negócio e seguindo as melhores práticas para fluxo de dados.

Anteriormente desenvolvido pela [US National Security Agency (NSA)](https://www.nsa.gov/){:target="_blank" rel="noopener"}, atualmente é mantido e desenvolvido pela [Apache Software Foundation](https://www.apache.org/){:target="_blank" rel="noopener"}


**Principais conceitos:**
* FlowFile
* Processador FlowFile
* Conexão
* Controlador de Fluxo
* Grupo de Processo

**Principais características:**
* Extração de dados de diversas fontes (sistemas terceiros, API's...) e crie seus próprios arquivos de fluxo
* Controle em tempo real para gerenciar o fluxo de dados entre qualquer origem e destino
* Visualização do DataFlow
* Possibilidade de utilização a bibliotecas existentes e funcionalidades do ecossistema Java, entre outros
* Foi projetado para escalar em Clusters, oferecendo escalabilidade e entrega garantida dos dados
* Visualize e monitore o desempenho

Para quem está familiarizado com desenvolvimento Java, o Apache Nifi permite customizações, ideal para criação de algum processador específico, posteriormente ganhando desempenho e velocidade no desenvolvimento da integração.

>Em resumo, o Apache NiFi é um software altamente confiável e escalável de alto desempenho para fluxo de dados, seja para integração entre sistemas, consumo/coleta de dados para tomada de decisões ou até mesmo para automatização e IoT.

Referências:<br>
[Apache NiFi Docs](http://nifi.apache.org/docs.html){:target="_blank" rel="noopener"}<br>
[Rapadura Tech](https://medium.com/rapaduratech/crie-seu-dataflow-com-apache-nifi-88e50ee8a3d8){:target="_blank" rel="noopener"}<br>

Repositório oficial:<br>
[apache/nifi](https://github.com/apache/nifi){:target="_blank" rel="noopener"}<br>