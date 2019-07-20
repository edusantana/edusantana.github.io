---
layout: post
title: "Asciidoc references with page indication"
description: ""
category: "asciidoc"
tags: [asciidoc,reference,page,docbook]
example1: Rakefile
---
{% include JB/setup %}

This solution if for asciidoc **with dblatex**.

### Quick review

    wget http://edusantana.github.io/asciidoc/page/pageconfig.adoc
    wget http://edusantana.github.io/asciidoc/page/simple-reference-with-page.adoc
    a2x -f pdf pageconfig.adoc
    a2x -f pdf simple-reference-with-page.adoc

### Let's start with a simple solution

Setting the `insert.xref.page.number` param to `yes`. You can do this
adding this comment to your asciidoc document:


    // a2x:  --dblatex-opts "-P insert.xref.page.number=yes"


Here's an example:

    = Simple reference with page =
    :doctype: book
    //    a2x: --dblatex-opts "-P insert.xref.page.number=yes"

    == Alfa

    See <<UsingMouse>>.

    [[UsingMouse]]
    == Using Mouse

    Et nobis voluptas voluptatem sapiente facilis voluptas.


![screenshot1]({{ site.url }}/assets/img/asciidoc/simple-reference-with-page.png)

### Solution with xref attributes

You can play with `xrefstyle` attribute of `xref`:

    = Understands page reference with asciidoc and dblatex =
    :doctype: book

    == Alfa

    See <<MouseButtons>>.

    === pageabbrev

    ++++
    <simpara>
    <xref linkend="MouseButtons" xrefstyle="pageabbrev"/>
    </simpara>
    ++++

    === template:the chapter numbered

    See 
    +++<xref linkend="MouseButtons" 
    xrefstyle="template:the section numbered %n"/>+++
    for more information.

    === select: labelnumber quotedtitle

    See
    +++<xref linkend="MouseButtons" 
          xrefstyle="select: labelnumber quotedtitle"/>+++

    === select: label pageabbrev quotedtitle

    Look at 
    +++<xref linkend="MouseButtons" 
          xrefstyle="select: label pageabbrev quotedtitle"/>+++
          
    [[MouseButtons]]
    === Learn Mouse Buttons

    Voluptatem qui consequatur quis.

![screenshot2]({{ site.url }}/assets/img/asciidoc/xref-with-attributes.png)


## Reference

* [insert.xref.page.number](http://docbook.sourceforge.net/release/xsl/1.78.0/doc/fo/insert.xref.page.number.html)
* [CustomXrefs](http://www.sagehill.net/docbookxsl/CustomXrefs.html)
* [CustomGentext](http://www.sagehill.net/docbookxsl/CustomGentext.html#CustomGenText)
* [http://www.methods.co.nz/asciidoc/publishing-ebooks-with-asciidoc.html](http://www.methods.co.nz/asciidoc/publishing-ebooks-with-asciidoc.html)
* [http://www.sagehill.net/docbookxsl/CrossRefs.html](CrossRefs)
* [https://groups.google.com/forum/#!topic/asciidoc/x8x9R7B1atE](https://groups.google.com/forum/#!topic/asciidoc/x8x9R7B1atE)
