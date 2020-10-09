---
layout: post
title:  "UPE: Vectores/Arreglos en ANSIC"
date:   2020-09-17 10:23:44 -0300
categories: UPE Vectores/Arreglos en ANSIC
excerpt_separator: <!--more-->
---

A veces queremos que nuestro programa obtenga números de forma aleatoria, por ejemplo, para simular una tirada de dados o el reparto de cartas en un juego. <!--more--> 
Los arreglos son estructuras de datos consistentes en un conjunto de datos del mismo tipo. Los arreglos tienen un tamaño que es la cantidad de objetos del mismo tipo que pueden almacenar. Los arreglos son entidades estáticas debido a que se declaran de un cierto tamaño y conservan ´este todo a lo largo de la ejecución del programa en el cual fue declarado.

Intente desarrollar los siguientes ejercicios utilizando lo aprendido en clase con lenguaje C. En caso de recurrir a Internet recuerde para que ejercicio tuvo que hacerlo y que fue lo que necesito buscar.

## Vectores:

### 1- Random y vectores
Rellene un vector de enteros de 10 posiciones con valores random. Al final, solo imprima los indices 1, 6 y 8.

{% highlight c++ %}
short i=0;
short A[10];

while(i<10)
{
    A[i] = rand() % 10;
    i++;
}

i=0;

printf("El valor de la pos %hd es %hd \n", 1, A[1]);
printf("El valor de la pos %hd es %hd \n", 6, A[6]);
printf("El valor de la pos %hd es %hd \n", 8, A[8]);
{% endhighlight %}

### 2- Imprimir todas las posiciones de un vector
Del ejercicio anterior, imprima ademas, todos los valores del vector.

{% highlight c++ %}
while(i<10)
{
    printf("El valor de la pos %hd es %hd \n", i, A[i]);
    i++;
}
{% endhighlight %}

### 3- Cargar un vector por teclado
Crear un vector de 5 posiciones enteras, y rellene las posiciones con números ingresados por teclado. Una vez llegado al final, imprimirlos en pantalla.

{% highlight c++ %}
short B[5];
i=0;
while(i<5)
{
    printf("Ingrese valor para la pos %hd \n", i);
    scanf("%hd",&B[i]);
    i++;
}

i=0;
while(i<5)
{
    printf("El valor de la pos %hd es %hd \n", i, B[i]);
    i++;
}
{% endhighlight %}

### 4- Sumar elementos de un vector
Del ejercicio anterior mostrar ademas la suma de todos los valores de cada posición del vector e imprimirlo en pantalla.

{% highlight c++ %}
i=0;
short ant=999;
while(i<5)
{
    if(ant>B[i])
        ant = B[i];
    
    i++;
}

printf("El valor minimo es: %hd \n", ant);
{% endhighlight %}

### 5- Vector y structs
Crear un vector de estructuras de 10 posiciones llamado “Alumnos” con datos enteros “cod_alumno” y “nota”. Llenar el vector con códigos de alumnos aleatorios y notas del 1 al 10. Al finalizar imprimir en pantalla los 10 códigos de alumno con sus notas.	

{% highlight c++ %}
    Hacerlo!!!!
{% endhighlight %}