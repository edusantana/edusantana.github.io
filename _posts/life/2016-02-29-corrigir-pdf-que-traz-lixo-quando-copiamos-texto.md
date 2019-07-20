---
layout: post
title: "Corrigir pdf que traz lixo quando copiamos texto"
description: ""
category: "life"
tags: ["pdf","copy"]
---
{% include JB/setup %}


AS vezes tentamos copiar um texto do pdf e ele trás caracteres loucos durante a cópia.
Isso acontece porque o sistema não possui as fontes anexadas no pdf instaladas.

Solução: [extrair as fontes do pdf](http://www.extractpdf.com) e instalar no sistema.

No opensuse a instalação das fontes basta copiar os arquivos para `~/.fonts`


## Reference

- [How can I extract embedded fonts from a PDF as valid font files?](http://stackoverflow.com/questions/3488042/how-can-i-extract-embedded-fonts-from-a-pdf-as-valid-font-files)
- [Opensuse: Chapter 14. Installing and Configuring Fonts for the Graphical User Interface](http://doc.opensuse.org/documentation/html/openSUSE_114/opensuse-reference/cha.fontconfig.html)
