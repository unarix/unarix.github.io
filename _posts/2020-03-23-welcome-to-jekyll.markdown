---
layout: post
title:  "Instalando Jekill para GitHub"
date:   2020-03-23 15:03:59 -0300
categories: tuto Jekill
---
Aca va en 10 pasos simples como tener funcionando `Jekill` sobre `Linux Mint` en mi caso esty usando 19.3:

  1- Abrir una terminal!

  2- Antes de instalar Jetkill debemos comprobar que tenemos instalado Ruby:

  `ruby -v`

  3- Ahora debemos checkear que esta instalado Gem

  `gem -v`

  4- Si los pasos anteriores no te dan error, puedes continuar con la instalacion de jetkill:

  `gem install jekyll bundler`

  5- Una vez finalizado vemos si l siguiente comando retorna una version o un error:

  `jekyll -v`

  6- Ahora podemos crear el nuevo site dentro de un directorio cualquiera (pero es importante que este vacio):

  `jekyll new 20percent`
  
  7- Una vez que la creacion de los archivos finalice podemos correrlo con el comando:
  
  `bundle exec jekyll serve`
  
  8- Comprueba que esta corriendo mediante un navegador, la url suele ser:
  
  `http://127.0.0.1:4000/`
  
  9- Es hora de editar:
  
  `Dentro de la carpeta *posts* se alojan todos los markdown de posteos.`

  `Dentro de la carpeta *site*, estan los archivos plantilla del sitio`
  
  10- Ahora sigue las instrucciones para publicarlo en el repo de github:
  
  `https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll#creating-your-site`

Eso es todo, con estos 10 pasos deberias poder tener a jekill funcionando.