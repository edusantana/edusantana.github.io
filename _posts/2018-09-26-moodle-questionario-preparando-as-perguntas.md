---
layout: post
title: "Moodle Questionário: preparando as perguntas para inserir no moodle"
description: "Antes de importar questões "
categories: ["Educação","ead","Moodle"]
tags: ["moodle","questionário","gift"]
---
{% include JB/setup %}

# Resumo rápido

- Criar arquivo txt com as questões;
- Adicionar `{T}` para questões *verdadeiras* e `{F}` para as *falsas*;
- Questões são **separadas por uma linha em branco**;
- Questões possuem um nome, especificados assim: `::nome da questão::`

Exemplo:

```
::processador:: As placas mães não irão ligar caso o processador 
não esteja conectado corretamente.{T}

::espuma:: É recomendável colocar uma espuma antiestática (que vem na 
embalagem da placa-mãe) entre a placa-mãe e o chassi metálico do 
gabinete para evitar descargas elétricas.{F}

::sata:: Para que os CD-ROMs ou HD funcionem, é necessário conectar 
o cabo SATA e o de energia.{T}
```

Baixe [o arquivo completo aqui](/assets/txt/prova-moodle.gift.txt).

<!--

# Post em elaboração

# Elaborando questões de verdadeiro ou falso

O tipo de questão mais fácil de elaborar é a de verdadeiro ou falso (_true or false_). Eu costumo fazê-la baseado em um livro ou apostila, pego alguns trechos dele na integra ou realizo pequenas modificações (para tornar falso).

Vejamos um exemplo, vamos pegar alguns trechos  e [esse]:

a. Questões de informática

	kjhkjhkjh . kjhg kj.

[Nesse livro](https://github.com/ufpb-computacao/linguagem-de-programacao-i-livro/releases/download/v1.0.2/linguagem-de-programacao-i-livro-v1.0.2.pdf) temos o seguinte trecho:

> C é uma linguagem Case Sensitive, isto é, letras maiúsculas e minúsculas fazem diferença.

Esta afirmação é verdadeira. Por

b. Questão de humanas

Para os colegas da área de Humanas Como esta [no livro](https://github.com/ufpb-computacao/fundamentos-socio-historico-da-educacao-livro/releases/download/v1.0.6/fundamentos-socio-historico-da-educacao-livro-v1.0.6.pdf):

> Como chama atenção Durkheim, se esta grande diferenciação entre os indivíduos é real, então o que
os une não pode partir logicamente de nenhum indivíduo isoladamente ou mesmo de um grupo de
indivíduos. O elemento responsável pela manutenção da coesão social deve ser algo distinto da esfera
individual, ou seja, deve estar localizado em uma esfera que seja, eminentemente coletiva.
>
> Este elemento de coesão é chamado por Durkheim de Fato Social, que será a principal unidade de
análise de sua teoria e a chave para a explicação do mundo social.

Como uma questão de verdadeiro ou falso poderia ser elaborada relativo a esse trecho:

> Para Durkheim, o elemento responsável pela manutenção da coesão social deve ser algo distinto da esfera
> individual, ou seja, deve estar localizado em uma esfera que seja, eminentemente coletiva. Este elemento 
> de coesão é chamado por Durkheim de Fato Social.


-->
