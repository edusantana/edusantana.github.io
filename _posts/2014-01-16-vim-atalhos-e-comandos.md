---
layout: post
title: Comandos e atalhos do Vim
tags: vim
categories: [linux]
---

Nesta postagem tentarei manter alguns atalhos e comandos do vim.
Alguns comandos são registrados para eu não esquecer-me deles.

Comandos com `^` significa `CTRL`, então `^F` significa `CTRL+F`.

Os comandos serão adicionados aos poucos.

* [Movendo-se](#movendose)
* [Ações](#aes)

## Movendo-se

- Avança Tela: `^F` - Scroll forward one screen.
- Retrocede Tela: `^B` - Scroll backward one screen.
- Avança Metade: `^D` - Scroll forward half screen (down).
- Retrocede Metade: `^U` - Scroll backward half screen (up).
- Última edição: `'.`
- Para linha 1: `1G`, final do arquivo: `0G`.

Não confundir comandos a seguir com zoom:

- Tela na primeira linha: `z ENTER` - Move current line to top of screen and scroll.
- Tela no centro: `z.` - Move current line to center of screen and scroll.
- Tela na última linha: `z-` - Move current line to bottom of screen and scroll.

## Dividindo a tela

- Horizonal: `:split`
- Vertical: `:vsplit`
- Fechar tela: `:close`

##Ações

- Juntar duas linhas: J *join*

##Repetindo

- Repetindo último comando: `.`
- Desfazer: `u`
- Refazer desfazer: `^r`

## Aplicando syntax e highlight

    :set syntax=markdown

## Referências

* Learning the vi and Vim Editors - SEVENTH EDITION
* [VIM Keyboard Shortcuts](http://www.keyxl.com/aaa8263/290/vim-keyboard-shortcuts.htm)
* [Vim Commands Cheat Sheet](http://bullium.com/support/vim.html)
* [Vim Magic - A handy guide to Vim shortcuts](http://eastcoastefx.vaesite.com/vim)
* [shortcutFoo](https://www.shortcutfoo.com/) - [vim](https://www.shortcutfoo.com/app/tutorial/vim)
* [syntax](http://stackoverflow.com/questions/10964681/enabling-markdown-highlighting-in-vim)
