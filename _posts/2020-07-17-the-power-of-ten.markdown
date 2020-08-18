---
layout: post
title:  "UPE: Los diez mandamientos de la NASA para escribir código - Teoria"
date:   2020-07-17 10:04:39 -0300
categories: UPE programacion mandamientos nasa código ansic
excerpt_separator: <!--more-->
---

Hace unos años, en 2006, la NASA lanzo un documento en el que sugieren sus 10 reglas para escribir sistemas críticos, es decir, código de alta calidad,<!--more--> mantenible y menos propenso a los fallos.

>Las reglas están pensadas para el lenguaje C/C++, pero son bastante generales y se pueden aplicar a cualquier lenguaje y sistema, deberíamos hacerle caso aunque no se trate de sistemas críticos. La mayoría de las reglas son de puro sentido común, pero lo cierto es que luego, en muchas ocasiones, no las aplicamos.

## Resumen:

### 1- Evita las construcciones de flujo complejas, como GOTO y la recursividad.
**Usar GOTO es una mala práctica**, existen diversos modos de evitar su uso, aunque en algunos casos parezca más rápido y que podría ahorrar espacio o trabajo el hecho de usar GOTO, definitivamente a la hora de hacer mantenimiento en aplicaciones extensas o no desarrolladas por uno mismo, es mucho más complejo de analizar o extender si dichas aplicaciones poseen internamente el uso de esta instrucción.
La recursividad se debe usar cuando sea realmente necesaria, es decir, cuando no exista una solución iterativa simple.

### 2- Todos los bucles deben tener límites fijos.
Por definición **un bucle debe contener condiciones que establezcan cuándo empieza y cuándo termina**, de manera que, mientras las condiciones se cumplan, ejecute una secuencia de código de manera repetitiva. En el caso de ciclo infinito, como la condición de finalización no se alcanza, el bucle sigue ejecutando el segmento de código indefinidamente.

### 3- Evita el uso de asignación dinámica de memoria después de la inicialización (malloc). 
Esto, en lenguajes con garbage-collector o similares es menos crítico, pero aún así es posible crear fugas de memoria si no somos cuidadosos. Además, **la asignación dinámica no es recomendable por la degradación de performance**; siempre que puedas, evitarlo.

### 4- Ninguna función debería ser tan larga que no pueda imprimirse en una sola carilla de una hoja. 
Esto es, como mucho unas **60 líneas** sin contar comentarios.

### 5- La densidad media de aserciones/excepciones en un código debería ser de al menos 2 por función. 
Las excepciones se utilizan para verificar situaciones anómalas en el código, que no deberían darse nunca en situaciones normales. En C++ es recomendable que haya al menos 2 por función.

### 6- Las variables deberían tener siempre el menor ámbito posible. 
Es decir, no le otorgamos más ámbito a una variable del que necesita, ya que podría ser modificada por otro código que no tuvimos en cuenta. **Evita siempre las variables globales**.

### 7- Verificar siempre parámetros y valores de retorno. 
Todas las llamadas a una función que devuelvan algo deberían ser comprobadas desde la función llamante para verificar que devuelven valores aceptables. Del mismo modo todos los parámetros que se pasan a una función deberían ser comprobados por ésta al principio de la misma. 

Esta recomendación está orientada a programas críticos, el impacto sobre la performance de comprobar variables en cada función debe ser fundada por la criticidad en el manejo de esos datos. **Para la gran mayoría de los casos basta con comprobar las variables luego del input del usuario**.


### 8- El uso del preprocesador se debe limitar a inclusiones de archivos de cabecera y definiciones de macros simples. 
Esto es más aplicable al mundo C/C++, pero se puede traducir en otros lenguajes en que **releguemos al mínimo el uso de compilaciones/regiones condicionales y otras complejidades** del compilador (por ejemplo, 10 directivas condicionales en un programa dan lugar a 2^10 versiones diferentes del mismo código, con la complejidad que ello conlleva para testearlo.

### 9- El uso de punteros debe mantenerse al mínimo.
Un error usando **un puntero puede bloquear el sistema**, y a veces puede ser difícil detectarlo. Muchos lenguajes no dejan usar punteros para evitar estos problemas, pero a la vez quitan parte del control que permite el lenguaje C.

### 10- Todo el código debe compilarse correctamente sin warnings desde el día uno. 
**Los compiladores admiten advertencias que están desactivadas de forma predeterminada, ya que la mayoría de los desarrolladores no las encuentran útiles.** En algunos casos, avisan sobre una elección de estilo o sobre funciones que pronto ya no serán soportadas o pertenecen a código antiguo. Algunas advertencias indican un área en la que los programadores a menudo realizan suposiciones incorrectas, lo que puede provocar un comportamiento inesperado o indefinido. 
**Es deseable que el compilador no emita estos warnings** ya que hará que el programa sea menos propenso a errores.

### Fuentes:
>
- [Wikipedia](https://en.wikipedia.org/wiki/The_Power_of_10:_Rules_for_Developing_Safety-Critical_Code)
- [NASA](http://lars-lab.jpl.nasa.gov/JPL_Coding_Standard_C.pdf)
- [Spinroot](http://spinroot.com/gerard/pdf/P10.pdf)