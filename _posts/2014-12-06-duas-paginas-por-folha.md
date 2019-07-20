---
layout: post
title: "Duas paginas por folha no pdf"
description: ""
category: "linux"
tags: pdf
---
{% include JB/setup %}


As vezes encontramos arquivos PDFs que não estão no tamanho A4, o 
seguinte comando redimenciona o arquivo para A4:


    gs -sDEVICE=pdfwrite -sPAPERSIZE=a4 -dFIXEDMEDIA -dPDFFitPage -dCompatibilityLevel=1.4 -o out.pdf input.pdf


O seguinte comando coloca duas páginas por folha:

    pdfnup --nup 2x2 --suffix '2x1' --batch input.pdf


## Referência

- [scaling-pdf-up-from-a4-to-a3-for-printing](http://superuser.com/questions/107741/scaling-pdf-up-from-a4-to-a3-for-printing)
