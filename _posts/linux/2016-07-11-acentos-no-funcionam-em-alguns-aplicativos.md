---
layout: post
title: "Acentos não funcionam em alguns aplicativos"
description: ""
category: "linux"
tags: ["acento","linux"]
---
{% include JB/setup %}

Primeiro temos que configurar o Layout do teclado apropriadamente.

Comigo o erro acontece da seguinte forma:

- O usuário tecla os acentos e em vez de apresentar `á`, apresenta `'a`.
- Alguns aplicativos funcionam o acento e outros não
- As vezes os acentos funcionam, no mesmo aplicativo, dependendo de como ele foi invocado.

Outras informações:

- Em inglês, o recurso que estamos procurando chama-se *Dead Keys*. 
- Geralmente este erro está associado ao `Ibus`.
- Verifique se o problema persiste ao abrir o programa pelo console ou pelo gestor de arquivos

# Problema com acentos no PDF-XChange Viewer

A solução consiste em invocar o `PDFXCview.exe` com a variável de ambiente `XMODIFIERS=""`.

Primeiro, recomendo testar a solução:

        $ cd ~/.wine/drive_c/Program\ Files/Tracker\ Software/PDF\ Viewer/
        $ XMODIFIERS="" wine PDFXCview.exe 

Abra um arquivo PDF e teste os acentos. Se funcionar, agora falta configurar para
quando clicar com o botão direito num arquivo PDF, o PDFXCview seja invocado com
a configuração apropriada.

Para isso, vamos modificar a linha de execução no arquivo `wine-extension-pdf.desktop`:

Precisei adicionar `XMODIFIERS=""` no comando do `Exec` e **reiniciar/restart** o computador.

        $ cat ~/.local/share/applications/wine-extension-pdf.desktop 
        [Desktop Entry]
        Type=Application
        Name=PDF-XChange Viewer
        MimeType=application/pdf;
        Exec=env WINEPREFIX="/home/eduardo/.wine" XMODIFIERS="" wine start /ProgIDOpen PDF-XChangeViewer.1 %f
        NoDisplay=true
        StartupNotify=true
        Icon=C055_PDFXCview.0

Pronto!

# Referências de soluções

- [https://www.codeweavers.com/support/wiki/linux/faq/Ubuntu/TrustyTahr#noaccents](https://www.codeweavers.com/support/wiki/linux/faq/Ubuntu/TrustyTahr#noaccents)

> The current temporary solution is to launch the application from terminal with an environment variable that turns ibus modifiers off. In terminal, give the command:

        XMODIFIERS="@im-none" /opt/cxoffice/bin/wine --bottle $BOTTLENAME --cx-app $EXECUTABLE.exe

- [http://ubuntuforum-br.org/index.php?topic=112582.0](http://ubuntuforum-br.org/index.php?topic=112582.0)

Segue a descrição do sistema que estou utilizando:

    uname -a
    Linux mpgoa-Vostro-V130 4.4.0-28-generic #47-Ubuntu SMP Fri Jun 24 10:09:13 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

Alguns comandos para configuração do teclado:

        sudo dpkg-reconfigure locales
        sudo dpkg-reconfigure console-setup
        sudo dpkg-reconfigure console-data
        sudo dpkg-reconfigure keyboard-configuration
        sudo dpkg-reconfigure tzdata

- [https://gist.github.com/marciomazza/7158411](https://gist.github.com/marciomazza/7158411)

Como ubstituir "ć" por "ç" e "Ć" por "Ç"


