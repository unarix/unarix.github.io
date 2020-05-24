---
layout: post
title:  "UPE: Archivos en ANSI C - Teoria"
date:   2020-05-24 17:09:05 -0300
categories: UPE archivos ansic
excerpt_separator: <!--more-->
---

Ahora veremos una guiá como refuerzo del material de catedra. Así como aprendimos la salida y entrada por pantalla y teclado, veremos ahora la entrada y/o salida de datos utilizando `Archivos`<!--more-->, lo cual será imprescindible para un gran número de aplicaciones que querramos desarrollar.

## Que son los archivos
Llamamos “archivo” al elemento de información compuesto por una suma de registros (combinaciones de bytes). Los archivos informáticos, en general, tienen algunas características en común:

- **Nombre:** Cada archivo es identificable con un nombre, que no puede coincidir con otro que esté en la misma ubicación.
- **Extensión:** Los archivos llevan una extensión opcional, que muchas veces indica su formato.
- **Tamaño:** Como se dijo, están compuestos por una serie de bytes que determinan su tamaño. Puede alcanzar kilobytes, megabytes, gigabytes.
- **Descripción:** Además del nombre y la extensión, suelen tener otras características. Dentro de estas características puede aparecer la protección del archivo, lo que significa el permiso limitado para la lectura o modificación. 
- **Ubicación:** La mayoría se encuentran almacenados en discos rígidos, que están ordenados. jerárquicamente en carpetas y subcarpetas.
- **Formato:** El modo en que el archivo será interpretado depende de su formato, entre los que están los formatos de texto, ejecutable, de datos, de imagen, de audio, de video, entre muchísimos otros.
- **Tipos**: Binarios y de texto.


## Que funciones se utilizan
El estándar de C contiene varias funciones para la edición de archivos, éstas están definidas en la cabecera `stdio.h` y por lo general empiezan con la letra f, haciendo referencia a `file`. Adicionalmente se agrega un tipo FILE, el cual se usará como puntero a la información del archivos. La secuencia que usaremos para realizar operaciones será la siguiente:

1. Crear un puntero del tipo `FILE *`
2. Abrir el archivo utilizando la función `fopen` y asignándole el resultado de la llamada a nuestro puntero.
3. Hacer las diversas operaciones (lectura, escritura, etc).
4. Cerrar el archivo utilizando la función `fclose`.

# fopen

Esta función sirve para abrir y crear archivos en disco. El prototipo correspondiente de fopen es:

{% highlight c++ %}
FILE * fopen (const char *filename, const char *opentype);
{% endhighlight %}

Los parámetros de entrada de fopen son:
- **filename:** una cadena que contiene un nombre de archivo válido. 
- **opentype:** especifica el tipo de archivo que se abrirá o se creará.

Una lista de parámetros opentype para la función fopen son:

- **"r"** : abrir un archivo para lectura, el archivo debe existir.
- **"w"** : abrir un archivo para escritura, se crea si no existe o se sobreescribe si existe.
- **"a"** : abrir un archivo para escritura al final del contenido, si no existe se crea.
- **"r+"** : abrir un archivo para lectura y escritura, el archivo debe existir.
- **"w+"** : crear un archivo para lectura y escritura, se crea si no existe o se sobreescribe si existe.
- **"r+b ó rb+"** : Abre un archivo en modo binario para actualización (lectura y escritura).
- **"rb"** : Abre un archivo en modo binario para lectura.

# fclose
Esta función sirve para poder cerrar un archivo que se ha abierto. El prototipo correspondiente de fclose es:
archivo 
{% highlight c++ %}
int fclose (FILE *stream);
{% endhighlight %}

Un valor de retorno cero indica que el archivo ha sido correctamente cerrado, si ha habido algún error, el valor de retorno es la constante EOF.

Un ejemplo para abrir y cerrar el archivo llamado `archivo.$$$` en modo lectura podría ser:

{% highlight c++ %}
    #include <stdio.h>
    #include <stdlib.h>
    
    int main()
    {
        FILE *archivo;
        archivo = fopen("archivo.$$$", "r");    

        if (archivo==NULL) 
        {
            printf("error"); 
            exit (1);
        }
        
        fclose ( archivo );

        return 0;
    }
{% endhighlight %}

>Importante: se utilizó el opentype "r", que es para la lectura.

Otra cosa importante es que el lenguaje C no tiene dentro de si una estructura para el manejo de excepciones o de errores, por eso es necesario comprobar que el archivo fue abierto con éxito `if (fp == NULL)`. Si fopen pudo abrir el archivo con éxito devuelve la referencia al archivo `(FILE *)`, de lo contrario devuelve `NULL` y en este caso se deberá revisar la dirección del archivo o los permisos del mismo. En estos ejemplos solo vamos a dar una salida con un retorno de 1 que sirve para señalar que el programa termino por un error.

# feof

Esta función sirve para determinar si el cursor dentro del archivo encontró el final (end of file). Existe otra forma de verificar el final del archivo que es comparar el carácter que trae `fgetc` del archivo con el macro EOF declarado dentro de `stdio.h`, pero este método no ofrece la misma seguridad (en especial al tratar con los archivos "binarios"). La función `feof` siempre devolverá cero (**Falso**) si no es encontrado **EOF** en el archivo, de lo contrario regresará un valor distinto de cero (**Verdadero**). El prototipo correspondiente de feof es:

{% highlight c++ %}
int feof(FILE *fichero);
{% endhighlight %}

# rewind
Literalmente significa "rebobinar", sitúa el cursor de lectura/escritura al principio del archivo.

El prototipo correspondiente de rewind es:
{% highlight c++ %}
void rewind(FILE *fichero);
{% endhighlight %}

# fwrite
Esta función está pensada para trabajar con registros de longitud constante y forma pareja con `fread`. Es capaz de escribir hacia un archivo uno o varios registros de la misma longitud almacenados a partir de una dirección de memoria determinada. El valor de retorno es el número de registros escritos, no el número de bytes. Los parámetros son: un puntero a la zona de memoria de donde se obtendrán los datos a escribir, el tamaño de cada registro, el número de registros a escribir y un puntero a la estructura `FILE` del archivo al que se hará la escritura.

El prototipo correspondiente de `fwrite` es:
{% highlight c++ %}
size_t fwrite(void *puntero, size_t tamano, size_t cantidad, FILE *archivo);
{% endhighlight %}

Un ejemplo concreto del uso de `fwrite` con su contraparte `fread` y usando funciones es:

{% highlight c++ %}
    #include <stdio.h>
    
    int main ()
    {
        FILE *archivo;
        
        char cadena[] = "Ejemplo de como escribir en un archivo.\n";
        
        archivo = fopen ( "archivo.txt", "r+" );

        fwrite( cadena, sizeof(char), sizeof(cadena), archivo );
        
        fclose ( archivo );
        
        return 0;
    }
{% endhighlight %}

<br>

# Próximos pasos

En la próxima guiá programaremos ejercicios utilizando estas funciones. 

> Mas data: [Programación en C/Manejo de archivos][msk]

[msk]: https://es.wikibooks.org/wiki/Programaci%C3%B3n_en_C/Manejo_de_archivos
