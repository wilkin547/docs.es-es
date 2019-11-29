---
title: Introducción a F# en Visual Studio
description: Obtenga información sobre cómo F# usar con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552827"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introducción a F# en Visual Studio

F#y las herramientas F# visuales se admiten en el IDE de Visual Studio.

Para empezar, asegúrese de que tiene [Visual Studio instalado con F# ](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos más básicos de Visual Studio es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez que Visual Studio está abierto:

1. En el menú **archivo** , elija **nuevo**y, a continuación, elija **proyecto**.

2. En el cuadro de diálogo nuevo proyecto, en **plantillas**, debería **Ver F#visual** .  Elija esta opción para mostrar F# las plantillas.

3. Seleccione **aplicación de consola de .net Core** o **aplicación de consola**.

4. Elija el botón **Aceptar** para crear el F# proyecto.  Ahora debería ver un F# proyecto en el explorador de soluciones.

## <a name="writing-your-code"></a>Escritura del código

Vamos a empezar por escribir código primero.  Asegúrese de que el archivo de `Program.fs` está abierto y, a continuación, reemplace el contenido por lo siguiente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, se ha definido una función `square` que toma una entrada denominada `x` y la multiplica por sí misma.  Dado F# que utiliza la [inferencia de tipos](../language-reference/type-inference.md), no es necesario especificar el tipo de `x`.  El F# compilador entiende los tipos en los que la multiplicación es válida y asignará un tipo a `x` basándose en cómo se llama a `square`.  Si mantiene el mouse sobre `square`, debería ver lo siguiente:

```fsharp
val square: x:int -> int
```

Esto es lo que se conoce como la firma de tipo de la función.  Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero".  Tenga en cuenta que el compilador dio `square` el tipo de `int` por ahora: esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino que es genérica en un conjunto cerrado de tipos.  El F# compilador eligió `int` en este punto, pero ajustará la firma del tipo si llama a `square` con un tipo de entrada diferente, como un `float`.

Otra función, `main`, se define, que está decorada con el atributo `EntryPoint` para indicar F# al compilador que la ejecución del programa debe comenzar allí.  Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).

En esta función se llama a la función `square` con un argumento de `12`.  A F# continuación, el compilador asigna el tipo de `square` que se va a `int -> int` (es decir, una función que toma un `int` y genera un `int`).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que se corresponden con los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución del código

Puede ejecutar el código y ver los resultados presionando **Ctrl**+**F5**.  Esto ejecuta el programa sin depuración y permite ver los resultados.  Como alternativa, puede elegir el elemento de menú **depurar** de nivel superior en Visual Studio y elegir **iniciar sin depurar**.

Ahora debería ver lo siguiente en la ventana de la consola que Visual Studio ha extraído:

```console
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer F# proyecto en Visual Studio, ha escrito una F# función que ha impreso los resultados de la llamada a esa función y ejecutado el proyecto para ver algunos resultados.

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md)por, que cubre algunas de las características principales del F# lenguaje.  Le proporcionará una visión general de algunas de las funcionalidades de F#y proporcionará ejemplos de código que puede copiar en Visual Studio y ejecutar.  También puede obtener más información sobre la F# documentación en la [ F# Página principal de docs](../index.yml).

## <a name="see-also"></a>Vea también

- [Paseo por F](../tour.md)
- [F#Referencia del lenguaje](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y operadores](../language-reference/symbol-and-operator-reference/index.md)
