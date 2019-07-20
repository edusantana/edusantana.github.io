---
layout: post
title: "Add a table of contains for each chapter with Asciidoc, dblatex and minitoc"
description: "This article a describes a manual solution to produce/generate a  table of contents (or a mini summary) for each chapter with asciidoc,  dblatex and minitoc."
category: "asciidoc"
tags: ["ebook","dblatex","asciidoc","minitoc"]
---
{% include JB/setup %}

This article a describes solutions to produce/generate a 
table of contents (or a mini summary) for each chapter with asciidoc, 
dblatex and minitoc.

## Automatic solution

**NOTE**: Thanks to **ben.guillon**, at dblatex forum, for sharing this solution.

### Solution overview

- edit `asciidoc.sty`
- run `a2x` as you always do

### Editing asciidoc.sty

Add the following code at the end of your `asciidoc.sty` file:

{% raw %}
    \usepackage[brazilian]{minitoc}

    \let\origchapter\chapter

    \def\chapter{%
      \@ifstar{\tchapter@s}{\tchapter@u}}

    \def\tchapter@u{%
      \@ifnextchar[{\tchapter@ui}%
                   {\tchapter@uii}}

    \def\tchapter@s{%
      \@ifnextchar[{\tchapter@si}%
                   {\tchapter@sii}}

    \def\tchapter@ui[#1]#2{%
      \origchapter[#1]{#2}%
      \minitoc}

    \def\tchapter@uii#1{%
      \origchapter{#1}%
      \minitoc}

    \def\tchapter@si[#1]#2{%
      \origchapter*[#1]{#2}%
      \minitoc}

    \def\tchapter@sii#1{%
      \origchapter*{#1}%
      \minitoc}

    \AtBeginDocument{\dominitoc}
{% endraw %}

That's it! Just run your `a2x` command and you will have a minitoc
at the beginning of each chapter.

*Downside*: With this solution you can't have any text 
(like chapter objectives) before it.

### Result

Look the result with the automatic solution:

![Automatic solution result]({{ site.url }}/assets/img/minitoc-automatic.png)

## Manual solution

This is the manual solution. With this you can place text before
minitoc.

*Downside*: It's a manual solution, you have to do it every time.

### Solution overview

- run dblatex with debug option `-d` (keeping the tex file at temp dir)
- load tex env
- manually edit the tex file
- run pdflatex over the edited tex file

### run dblatex with debug

Read [Debugging your Style](http://dblatex.sourceforge.net/doc/manual/sec-custom-latex.html#sec-debug).

Option 1: add the following option to your a2x command

        --dblatex-opts "-d"

Option 2: add to your asciidoc file:

        //    a2x: --dblatex-opts "-d"

After build it will print a message saying that the temporary directory wasn't
removed:

        /tmp/tpub-ben-99629 is not removed

### load tex env
Go to the temporary directory and load the tex env with:

        . env_tex

### manually edit the tex

Read [texblog.org/tag/minitoc](http://texblog.org/tag/minitoc), tip 10.

Go to the temp directory and edit the tex file.

* include `\usepackage[brazilian]{minitoc}` at the usepackge section
* include `\dominitoc` after ` \begin{document}`
* include `\minitoc` after `\chapter{...}`, where you want the minitoc to be generated

### running pdflatex

At the temporary directory run pdflatex:

        pdflatex yourfile.tex

That's it!

**NOTE**: If you forget to run `. env_tex` you will get an error like this:

      ! LaTeX Error: File `asciidoc-dblatex.sty' not found.

### Result

Look the result with the manual solution:

![Manual solution result]({{ site.url }}/assets/img/minitoc.png)

### References

* [dblatex/Debugging your Style](http://dblatex.sourceforge.net/doc/manual/sec-custom-latex.html#sec-debug)
* [texblog.org/tag/minitoc](http://texblog.org/tag/minitoc/)
* [minitoc manual](http://www.ctex.org/documents/packages/contents/minitoc.pdf)
* [dblatex.sourceforge.net/doc/manual/ref-dblatex.html](http://dblatex.sourceforge.net/doc/manual/ref-dblatex.html)
* [debian-handbook/blob/master/dblatex/librement.sty](https://github.com/n0rman/debian-handbook/blob/master/dblatex/librement.sty)
* [Asciidoc forum question](https://groups.google.com/forum/#!topic/asciidoc/hptLZtmz67Y)
* [dblatex forum question](http://sourceforge.net/p/dblatex/mailman/message/32257241/)
