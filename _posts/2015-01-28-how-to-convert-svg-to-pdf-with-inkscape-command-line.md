---
layout: post
title: "How to convert svg to pdf with inkscape command line"
description: ""
category: "asciidoc"
tags: [inkscape,convert,svg,pdf,linux,asciidoc,dblatex]
---
{% include JB/setup %}


Very often I need to save/export/convert a svg file to pdf to include
in a asciidoc book.

Here's the code to convert it:

    inkscape -z -D -d 300 --export-pdf=fig6.pdf "/home/santana/asciibook/agrarias/adoc/agrarias-vol3-ecologia-livro/releases/master/livro/images/cap2/fig6.svg"

If you are including images in asciidoc and using dbaletx to generate
the pdf you can skip the file extension:

    image::{img}/fig6[scaledwidth="50%"]

It will detect that `fig.svg` file exists and will generate a pdf file, but it will use the default 90 dpi. To change this, you can edit `/usr/local/lib/python2.7/dist-packages/dblatex-0.3.5-py2.7.egg/dbtexmf/core/imagedata.py` and add `-d 300` as the previous command.

### Reference


- [http://dblatex.sourceforge.net/doc/manual/sec-figinclude.html](http://dblatex.sourceforge.net/doc/manual/sec-figinclude.html)
- [http://fossies.org/dox/dblatex-0.3.5/imagedata_8py_source.html](http://fossies.org/dox/dblatex-0.3.5/imagedata_8py_source.html)
