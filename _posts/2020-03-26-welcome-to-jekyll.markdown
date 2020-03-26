---
layout: post
title:  "Programando Structs en C++"
date:   2020-03-26 01:09:59 -0300
categories: facu exe
---
El Objetivo de este  TP es practicar y resolver tres ejercicios vinculados al tema `STRUCTS`. Para poder resolverlos es necesario tener claro algunos conceptos: 

    • Librerías
    • Variables
    • Tipos de datos
    • Funciones
    • Estructuras de control
    • Structs
    • Vectores

Primer Ejercicio 

El dueño de un deposito de mercadería llamado Alexander, quiere mejorar su linea de almacenamiento; para esto decide que toda caja que ingrese sea inventariada tomando su ancho, largo, peso entre otros atributos; las cajas que nuestro cliente puede almacenar no pueden superar los 120 cm de alto, por lo tanto en la entrada de datos debemos descartar estas y darle aviso al operador. 

Cada caja tiene como atributos:
    • El numero de serie (10 dígitos)
    • Ancho (en cm)
    • Alto (en cm)
    • Peso (en gramos)

¿Puedes desarrollar un programa que permita el ingreso de 10 cajas descartando las que tengan como atributo “alto” mayor a 120 cm para luego imprimir el listado de cajas filtrado?

Codigo en c++:
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Segundo Ejercicio

Alexander nos pide que cada caja que se ingrese con un peso inferior a 570 gramos sea marcada como caja frágil automáticamente. De esta forma puede detectar cuales hay que tratarlas con cuidado y enviarlas a las estanterías mas próximas para que no se dañen en el traslado.

Nuevo atributo:
    • Frágil (si/no)

¿Podes agregarle al desarrollo anterior el nuevo atributo y marcarlo en SI con cada caja de peso inferior a 570 gramos?  La impresión de las cargas frágiles ahora saldrán discriminadas en una impresión aparte. 

Codigo en c++:
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Tercer Ejercicio

Nuestro magnate de las estanterías descubre que tiene un gran problema: su depósito es un caos. Por lo tanto nos solicita que el listado que se imprime en pantalla, este ordenado de mayor a menor para que las cajas mas pequeñas estén almacenadas en las estanterías mas cercanas y las mas voluminosas vallan al fondo, donde las estructuras se encuentran reforzadas.

Incluyendo las limitaciones de los ejercicios anteriores; ¿Podrías desarrollar un programa que permita ingresar un máximo de 10 cajas y listarlas ordenarlas por su tamaño de mayor a menor?

Codigo en c++:
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Material:
[Historia de c++][historia-C] / [Structs en c++][structs-C]

[structs-C]: http://www.investigacion.frc.utn.edu.ar/tecnicasdigitales/pub/File/Estructuras.pdf
[historia-C]:   https://es.wikipedia.org/wiki/C%2B%2B
