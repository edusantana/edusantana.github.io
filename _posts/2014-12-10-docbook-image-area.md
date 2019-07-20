---
layout: post
title: "How to add numbers to area of images with asciidoc"
description: "Adicionar letrar"
category: "asciidoc"
tags: [asciidoc,docbook,mediaobjectco,callout]
---
{% include JB/setup %}

## mediaobjectco

This solution is based on docbook tag `mediaobjectco`.

See:

- [mediaobjectco](http://www.docbook.org/tdg/en/html/mediaobjectco.html)
- [Imagemaps](http://www.sagehill.net/docbookxsl/Imagemaps.html)


```
++++
<mediaobjectco>
<imageobjectco>
<areaspec units="calspair">
<areaset id="oneway" coords="">
<area id="oneway1" coords="3000 4000"/>
<area id="oneway2" coords="3250 3400"/>
</areaset>
<area id="myhouse" coords="4250 5900"/>
</areaspec>
<imageobject>
<imagedata fileref="images/aprender-fazendo.png"/>
</imageobject>
</imageobjectco>
</mediaobjectco>
++++
```

The result will be numbers added to the image, as these arrows indicates:

![Use of mediaobjectco](/assets/img/asciidoc/mediaobjectco.png)

