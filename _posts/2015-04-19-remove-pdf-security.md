---
layout: post
title: "Remove PDF security"
description: ""
category: "life"
tags: pdf
---
{% include JB/setup %}

How to remove pdf security:

    ENCRYPTED_FILE=encrypted_file.pdf
    gs -q -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile="$ENCRYPTED_FILE"_unencrypted.pdf -c .setpdfwrite -f "$ENCRYPTED_FILE"

I use this when I need to make annotations on protected pdf files.

### Reference

- [http://www.cyberciti.biz/faq/removing-password-from-pdf-on-linux/](http://www.cyberciti.biz/faq/removing-password-from-pdf-on-linux/)
