---
layout: post
title: "Como criar imagem de CD ROM para distirbuição no linux/windows"
description: ""
category: "linux"
tags: ["cd-rom","distribuição"]
---
{% include JB/setup %}


Comando para gerar imagem para distribuição (compatível com vários sistemas operacionais):

    genisoimage -f -J -joliet-long -r -allow-lowercase -allow-multidot -o ~/mpgoa-cd-rom.iso /home/eduardo/Dropbox/mpgoa/2-cd-rom/mpgoa-cd-rom-imagem
