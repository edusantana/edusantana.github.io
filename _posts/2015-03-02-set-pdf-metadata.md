---
layout: post
title: "Set pdf metadata"
description: ""
category: "linux"
tags: pdf
---
{% include JB/setup %}

Reading file metadata:

    $ exiftool -a matematica-elementar-livro-v2.3.8.pdf 
    
    ExifTool Version Number         : 9.46
    File Name                       : matematica-elementar-livro-v2.3.8.pdf
    Directory                       : .
    File Size                       : 1723 kB
    File Modification Date/Time     : 2014:11:10 09:41:53-03:00
    File Access Date/Time           : 2015:03:02 12:48:46-03:00
    File Inode Change Date/Time     : 2014:12:15 20:33:48-03:00
    File Permissions                : rw-rw-r--
    File Type                       : PDF
    MIME Type                       : application/pdf
    PDF Version                     : 1.6
    Linearized                      : No
    Page Count                      : 224
    Creator                         : Sejda (Ver. 1.0.0.M9)
    Producer                        : iText 2.1.7 by 1T3XT
    Modify Date                     : 2014:11:10 09:33:01-03:00
    Create Date                     : 2014:11:10 09:33:01-03:00

    /Author (Nicola Talbot)
    /Title  (Creating a PDF document using PDFLaTeX)
    /CreationDate (D:20040502195600)
    /Subject (PDFLaTeX)
    /Keywords (PDF;LaTeX)

    /Title: title of the document 
    /Author: author of the document 
    /Creator: PDF creator 
    /Producer: PDF producer 
    /CreationDate: creation date 
    /ModDate: modification date 
    /Subject: subject of the document 
    /Keywords: keywords, separated by a semicolon (;) 
