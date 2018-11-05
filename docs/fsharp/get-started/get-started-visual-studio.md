---
title: 'Introducción a F # en Visual Studio'
description: 'Obtenga información sobre cómo usar F # con Visual Studio.'
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43872856"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introducción a F # en Visual Studio

Las herramientas de Visual F # y F # se admiten en el IDE de Visual Studio.

Para empezar, asegúrese de que tiene [instalado Visual Studio con F #](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos en Visual Studio más básicos es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez abierto Visual Studio:

1. En el **archivo** menú, elija **New**y, a continuación, elija **proyecto**.

2.  En el nuevo proyecto en el cuadro de diálogo, **plantillas**, debería ver **Visual F #**.  Elija esta opción para mostrar las plantillas de F #.

3. Seleccione **aplicación de consola de .NET Core** o **aplicación de consola**.

3. Elija la **bien** botón para crear el proyecto de F #!  Ahora debería ver un proyecto de F # en el Explorador de soluciones.

## <a name="writing-your-code"></a>Escribir el código

Vamos a empezar a escribir código en primer lugar.  Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace su contenido por lo siguiente:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada denominada `x` y lo multiplica por sí mismo.  Dado que F # utiliza [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.  El compilador de F # entiende los tipos que es válida la multiplicación y asignará un tipo a `x` según cómo `square` se llama.  Si se mantiene el mouse sobre `square`, debería aparecer lo siguiente:

```
val square: x:int -> int
```

Esto es lo que se conoce como la firma del tipo de la función.  Se puede leer como esta: "cuadrado es una función que toma un número entero denominado x y genera un número entero".  Tenga en cuenta que el compilador proporcionaba `square` el `int` tipo por ahora: Esto es porque no es genérica a través de la multiplicación *todas* tipos, pero es bastante genérico a través de un conjunto cerrado de tipos.  El compilador de F # seleccionado `int` en este punto, pero se ajustará la firma del tipo si se llama a `square` con otro tipo de entrada, como un `float`.

Otra función `main`, se ha definido, que está decorada con el `EntryPoint` atributo para indicar al compilador de F # esa ejecución del programa debe empezar por ahí.  Sigue la misma convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).

Se encuentra en esta función que llamamos el `square` función con un argumento de `12`.  El compilador de F #, a continuación, asigna el tipo de `square` sea `int -> int` (es decir, una función que toma un `int` y genera un `int`).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a lenguajes de programación de estilo C, los parámetros que corresponden a los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución del código

Puede ejecutar el código y ver resultados presionando **Ctrl**+**F5**.  Esto ejecuta el programa sin depurarlo y le permite ver los resultados.  Como alternativa, puede elegir el **depurar** en Visual Studio de elemento de menú de nivel superior y elija **iniciar sin depurar**.

Ahora debería ver lo siguiente que se imprimen en la ventana de consola que apareció Visual Studio:

```
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer proyecto de F # en Visual Studio, escribe que una función de F # imprime los resultados de una llamada a esa función y ejecute el proyecto para ver algunos resultados.

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo por F #](../tour.md), donde abordan algunas de las características principales del lenguaje F #.  Se ofrecerle una visión general de algunas de las capacidades de F # y se proporcionan ejemplos de código suficiente que puede copiar en Visual Studio y ejecutar.  También hay algunos excelentes recursos externos, puede usar, exhibió en el [Guía de F #](../index.md).

## <a name="see-also"></a>Vea también

- [Paseo por F](../tour.md)
- [Referencia del lenguaje F #](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y el operador](../language-reference/symbol-and-operator-reference/index.md)
