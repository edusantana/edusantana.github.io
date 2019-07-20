---
layout: post
title: "Criando link para postagens no Moodle"
description: ""
category: "ead"
tags: ["ead","moodle","link"]
---
{% include JB/setup %}

Quando estamos escrevendo nos fóruns do Moodle, as vezes queremos
fazer referência a postagens de outros colegas. A solução que irei
apresentar consiste em criar um link para referenciá-la.

* Teoria (âncora html)
* Descrobrindo a âncora de uma postagem
* Criando o link para a âncora da postagem

### Teoria

Para fazer isto será necessário reconhecer um pouco de HTML, não se assuste, é bem fácil.

Em HTML existe um recurso chamado **Âncora**, que marca uma região na página. Neste momento, vamos aprender a identificar uma âncora, vamos ver uns exemplos:

```html
    <a id="p1"></a>
    (...) (Postagem 1)
    <a id="p2"></a>
    (...) (Postagem 2)
    <a id="p416597"></a>
    (...) (Postagem 416597)
```

O endereço de uma âncora consiste no valor de `#` + o valor de `id`, vejamos os exemplos:

- `#p1` é o endereço para a âncora do início da postagem 1
- `#p2` é o endereço para a âncora do início da postagem 2
- `#p416597` é o endereço para a âncora do início da postagem 416597

### Descrobrindo a âncora de uma postagem

Agora que você já sabe como identificar uma âncora, o próximo passo será encontrar a âncora da postagem que você deseja referenciar.

* Dentro do fórum, você clica com o botão direito em cima do **assunto da postagem**, que neste caso era 'Re: Fórum temático 5: Mitos e verdade em EaD.'.
* E selecione **Inspecionar**.
* Irá aparecer uma tela abaixo com o código html. Suba um pouco até encontrar a âncora.

![Inspecionar para encontrar a âncora](/assets/img/inspecionar-para-copiar-ancora-da-mensagem.png)

Percebam o código da âncora na imagem:

```html
    <a id="p415876"></a>
```

### Criando o link para o endereço da âncora da postagem

Uma vez que você identificou o valor da âncora, neste caso era `p415876`, você precisará adicionar um `#` na frente, para fazer o endereço da âncora: `#p415876`.

Dentro do fórum, escolha uma mensagem qualquer e clique em responder. Dentro da caixa de texto da mensagem, faça selecione um trecho da sua mensagem e clique para inserir um link. Informe o endereço da âncora no campo *URL do link*, como indicado na imagem a seguir.

![Fazendo o link para a postagem](/assets/img/fazendo-o-link-para-a-postagem.png)

Quando você publicar sua postagem, seu link apontará para a postagem referenciada.

**NOTE:** Este método só funciona para mensagens dentro de um mesmo fórum. Para adicionar links para postagens de outro fórum, é necessário colocar o `endereço da discussão` + `#` + `Ancora`, exemplo: [http://pigead.lanteuff.org/mod/forum/discuss.php?d=4517#p344960](http://pigead.lanteuff.org/mod/forum/discuss.php?d=4517#p344960)
