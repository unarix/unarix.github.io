---
layout: post
title:  "A2K: Instalando Jekill para GitHub"
date:   2020-03-23 15:03:59 -0300
categories: tuto Jekill
excerpt_separator: <!--more-->
---

### 10 pasos para instalar jeKill y no morir en el intento
<!--more-->
Aca va en 10 pasos simples como tener funcionando `Jekill` sobre `Linux mint/ubuntu` en mi caso estoy usando Mint 19.3:

  1- Abrir una terminal!

  2- Antes de instalar Jetkill debemos comprobar que tenemos instalado Ruby:

  `ruby -v`

  3- Ahora debemos checkear que esta instalado Gem

  `gem -v`

  4- Si los pasos anteriores no te dan error, puedes continuar con la instalación de jetkill:

  `gem install jekyll bundler`

  5- Una vez finalizado vemos si l siguiente comando retorna una version o un error:

  `jekyll -v`

  6- Ahora podemos crear el nuevo site dentro de un directorio cualquiera (pero es importante que este vació):

  `jekyll new 20percent`
  
  7- Una vez que la creación de los archivos finalice podemos correrlo con el comando:
  
  `bundle exec jekyll serve`
  
  8- Comprueba que esta corriendo mediante un navegador, la url suele ser:
  
  `http://127.0.0.1:4000/`
  
  9- Es hora de editar:
  
  `Dentro de la carpeta *posts* se alojan todos los markdown de posteos.`

  `Dentro de la carpeta *site*, están los archivos plantilla del sitio`
  
  10- Ahora sigue las instrucciones para publicarlo en el repo de github:
  
  `https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll#creating-your-site`

Eso es todo, con estos 10 pasos deberías poder tener a jekill funcionando.