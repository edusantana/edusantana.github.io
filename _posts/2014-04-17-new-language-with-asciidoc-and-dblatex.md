---
layout: post
title: "New language with asciidoc and dblatex"
description: "How to add a new language to asciidoc"
category: asciidoc
tags: [asciidoc, dblatex, language]
---
{% include JB/setup %}

This post is to share how I was able to configure
a new language with source highlight with asciidoc.

You will only need this if you have created a new language
or you are writing about a language that dblatex doesn't support.

In my case I have created a pseudo-code language to teach algorithm, 
in portuguese. This is a simplified version of a language: `if=SE,
else=SENAO, then=ENTAO, write=ESCREVA, read=LEIA`. The ideia is to
highlight these keywords.

First let's download a new copy of asciidoc:

````
$ cd ~
$ git clone https://github.com/asciidoc/asciidoc myasciidoc 
````

Then we're going to configure the new language dbalatex style.
To create a new language called "pseudo" add the following to 
`myasciidoc/dblatex/asciidoc-dblatex.sty`:

````
\lstdefinelanguage{pseudo}
{
morekeywords={ENQUANTO,PARA,SE,SENAO,ENTAO},
morekeywords=[2]{LEIA,ESCREVA},
sensitive=true,
morecomment=[l]{//},
morecomment=[s]{/*}{*/},
morestring=[b]",
extendedchars=true,
keywordstyle=[2]{\color{black}\bfseries}
}
````

With the new language configured, the next step is to create 
a test file (`mylang_test.adoc`):



    == Testing new lang

    [source,pseudo]
    ----
    SE (x>2) ENTAO
      ESCREVA "Alguma coisa"
    SENAO
      LEIA "Outra coisa"
    ----


The last step will be to generate the pdf with dbalatex and using the 
custom asciidoc:

````
$ myasciidoc/a2x.py -f pdf mylang_test.adoc 
````

Here's how the final pdf looks like: 

![Final PDF](/assets/pseudo-lang.png)

### References

* [post](https://groups.google.com/forum/?fromgroups=#!topic/asciidoc/XZqi86pzQHE).
* [http://jevopi.blogspot.com.br/2011/10/latex-listings-definitions-for-modeling.html](http://jevopi.blogspot.com.br/2011/10/latex-listings-definitions-for-modeling.html)
* [add-keywords-to-an-existing-language-in-listings](http://tex.stackexchange.com/questions/115316/add-keywords-to-an-existing-language-in-listings)
* [listings.pdf](http://get-software.net/macros/latex/contrib/listings/listings.pdf)
