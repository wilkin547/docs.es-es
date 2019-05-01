---
title: Introducción a F# en Visual Studio
description: Aprenda a usar F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 9b02a5d295f982b1911dab567213fa9a2b6c4304
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808016"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introducción a F# en Visual Studio

F#y el objeto Visual F# se admiten las herramientas del IDE de Visual Studio.

Para empezar, asegúrese de que tiene [instaladas de Visual Studio con F# ](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos en Visual Studio más básicos es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez abierto Visual Studio:

1. En el **archivo** menú, elija **New**y, a continuación, elija **proyecto**.

2. En el nuevo proyecto en el cuadro de diálogo, **plantillas**, debería ver **Visual F#** .  Elija esta opción para mostrar el F# plantillas.

3. Seleccione **aplicación de consola de .NET Core** o **aplicación de consola**.

4. Elija la **bien** botón para crear el F# proyecto!  Ahora debería ver un F# proyecto en el Explorador de soluciones.

## <a name="writing-your-code"></a>Escribir el código

Vamos a empezar a escribir código en primer lugar.  Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace su contenido por lo siguiente:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada denominada `x` y lo multiplica por sí mismo.  Dado que F# usa [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.  El F# compilador entiende los tipos que es válida la multiplicación y asignará un tipo a `x` según cómo `square` se llama.  Si se mantiene el mouse sobre `square`, debería aparecer lo siguiente:

```fsharp
val square: x:int -> int
```

Esto es lo que se conoce como la firma del tipo de la función.  Se puede leer como esta: "Cuadrado es una función que toma un número entero denominado x y genera un número entero".  Tenga en cuenta que el compilador proporcionaba `square` el `int` tipo por ahora: Esto es porque no es genérica a través de la multiplicación *todas* tipos, pero es bastante genérico a través de un conjunto cerrado de tipos.  El F# compilador seleccionada `int` en este punto, pero se ajustará la firma del tipo si se llama a `square` con otro tipo de entrada, como un `float`.

Otra función `main`, se define, que está decorada con el `EntryPoint` atributo para indicar el F# compilador que la ejecución del programa debe empezar por ahí.  Sigue la misma convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).

Se encuentra en esta función que llamamos el `square` función con un argumento de `12`.  El F# compilador, a continuación, asigna el tipo de `square` sea `int -> int` (es decir, una función que toma un `int` y genera un `int`).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a lenguajes de programación de estilo C, los parámetros que corresponden a los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución del código

Puede ejecutar el código y ver resultados presionando **Ctrl**+**F5**.  Esto ejecuta el programa sin depurarlo y le permite ver los resultados.  Como alternativa, puede elegir el **depurar** en Visual Studio de elemento de menú de nivel superior y elija **iniciar sin depurar**.

Ahora debería ver lo siguiente que se imprimen en la ventana de consola que apareció Visual Studio:

```
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer F# proyecto en Visual Studio, escribe un F# función imprime los resultados de llamar a función y ejecutar el proyecto para ver algunos resultados.

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md), donde abordan algunas de las características principales de la F# lenguaje.  Se le ofrecerá una visión general de algunas de las capacidades de F#y proporcionan ejemplos de código suficiente que puede copiar en Visual Studio y ejecutar.  También hay algunos excelentes recursos externos, puede usar, exhibió en el [ F# guía](../index.md).

## <a name="see-also"></a>Vea también

- [Paseo por F](../tour.md)
- [F#referencia del lenguaje](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y el operador](../language-reference/symbol-and-operator-reference/index.md)
