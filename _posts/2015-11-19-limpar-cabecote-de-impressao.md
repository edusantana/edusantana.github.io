---
layout: post
title: "Limpar cabeçote de impressão da impressora Epson no linux"
description: "Como limpar o cabeçote da impressora epson no linux"
category: [linux,life,util]
tags: [impressora,epson,util]
---
{% include JB/setup %}


# Limpa o cabeçote de impressão

        sudo escputil -c -r /dev/usb/lp0

# Imprime folha de teste para alinhamento

        sudo escputil -n -r /dev/usb/lp0
        
# Ajuda do aplicativo

        man escputil

# Como realizar manutenção manual

- [http://linuxdicasesuporte.blogspot.com.br/2013/09/como-desentupir-cabecas-de-impressao.html](http://linuxdicasesuporte.blogspot.com.br/2013/09/como-desentupir-cabecas-de-impressao.html)


# Referências

- [http://www.vivaolinux.com.br/dica/Verificar-nivel-de-tinta-da-EpsonTX105-com-Escputil](http://www.vivaolinux.com.br/dica/Verificar-nivel-de-tinta-da-EpsonTX105-com-Escputil)
- [https://forums.opensuse.org/showthread.php/495158-Ink-level-on-Epson-Stylus-NX420-using-OpenSuse-13-1](https://forums.opensuse.org/showthread.php/495158-Ink-level-on-Epson-Stylus-NX420-using-OpenSuse-13-1)

