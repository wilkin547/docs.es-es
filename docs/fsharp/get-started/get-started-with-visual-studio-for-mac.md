---
title: Introducción a F# en Visual Studio para Mac
description: Aprenda a usar F# con Visual Studio para Mac.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331876"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Introducción a F# en Visual Studio para Mac

F#y el objeto Visual F# se admiten las herramientas de Visual Studio para Mac IDE. Asegúrese de que tiene [Visual Studio para Mac instalados](install-fsharp.md#install-f-with-visual-studio-for-mac).

## <a name="creating-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos en Visual Studio para Mac más básicos es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez abierto Visual Studio para Mac:

1. En el **archivo** menú, elija **nueva solución**.

2. En el cuadro de diálogo nuevo proyecto, hay 2 distintas plantillas de aplicación de consola.  Hay uno en otras opciones -> .NET que tiene como destino .NET Framework.  La otra plantilla está en .NET Core -> aplicación destinada a .NET Core.  Cualquier plantilla debería funcionar con el propósito de este artículo.

3. En la aplicación de consola, cambie C# a F# si es necesario.  Elija la **siguiente** botón para desplazarse hacia delante.  

4. Asigne un nombre al proyecto y elija las opciones que desee para la aplicación.  Tenga en cuenta, el panel de vista previa al lado de la pantalla que muestra la estructura de directorios que se creará en función de las opciones seleccionadas.  

5. Haga clic en **Crear**.  Ahora debería ver un F# proyecto en el Explorador de soluciones.

## <a name="writing-your-code"></a>Escribir el código

Vamos a empezar a escribir código en primer lugar.  Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace su contenido por lo siguiente:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada denominada `x` y lo multiplica por sí mismo.  Dado que F# usa [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.  El F# compilador entiende los tipos que es válida la multiplicación y asignará un tipo a `x` según cómo `square` se llama.  Si se mantiene el mouse sobre `square`, debería aparecer lo siguiente:

```
val square: x:int -> int
```

Esto es lo que se conoce como la firma del tipo de la función.  Se puede leer como esta: "Cuadrado es una función que toma un número entero denominado x y genera un número entero".  Tenga en cuenta que el compilador proporcionaba `square` el `int` tipo por ahora: Esto es porque no es genérica a través de la multiplicación *todas* tipos, pero es bastante genérico a través de un conjunto cerrado de tipos.  El F# compilador seleccionada `int` en este punto, pero se ajustará la firma del tipo si se llama a `square` con otro tipo de entrada, como un `float`.

Otra función `main`, se define, que está decorada con el `EntryPoint` atributo para indicar el F# compilador que la ejecución del programa debe empezar por ahí.  Sigue la misma convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).

Se encuentra en esta función que llamamos el `square` función con un argumento de `12`.  El F# compilador, a continuación, asigna el tipo de `square` sea `int -> int` (es decir, una función que toma un `int` y genera un `int`).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a lenguajes de programación de estilo C, los parámetros que corresponden a los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución del código

Puede ejecutar el código y ver los resultados, haga clic en **ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.  Esto ejecutará el programa sin depuración y le permite ver los resultados.

Ahora debería ver lo siguiente que se imprimen en la ventana de consola que apareció Visual Studio para Mac:

```
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer F# proyecto en Visual Studio para Mac, escribe un F# función imprime los resultados de llamar a función y ejecutar el proyecto para ver algunos resultados.

## <a name="using-f-interactive"></a>Uso de F# interactivo

Una de las mejores características del objeto Visual F# herramientas en Visual Studio para Mac es el F# ventana interactiva.  Permite enviar código a través de un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.

Para empezar a usarlo, resalte el `square` definida en el código de función.  A continuación, haga clic en **editar** en el menú de nivel superior.  A continuación, seleccione **Enviar selección a F# interactivo**.  Esto ejecuta el código en el F# ventana interactiva.  Como alternativa, puede haga clic con el botón derecho en la selección y elija **Enviar selección a F# interactivo**.  Debería ver el F# ventana interactiva aparecen con lo siguiente en él:

```
>

val square : x:int -> int

>
```

Esto muestra la misma firma de función para el `square` función, que vio anteriormente cuando al mantener el mouse sobre la función.  Dado que `square` ahora está definida en el F# proceso interactivo, podemos llamarlo con valores diferentes:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Esto ejecuta la función, el resultado se enlaza a un nuevo nombre `it`y muestra el tipo y el valor de `it`.  Tenga en cuenta que es preciso finalizar cada línea con `;;`.  Se trata cómo F# interactivo sabe cuando finalice la llamada de función.  También puede definir nuevas funciones en F# interactivo:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Lo anterior define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar.  Puede llamar a esta función para ver lo que devuelve con diferentes entradas.  Puede llamar a funciones dentro de las llamadas de función:

```
> isOdd (square 15);;
val it : bool = true
```

También puede usar el [operador de canalización hacia delante](../language-reference/symbol-and-operator-reference/index.md) para canalizar el valor en las dos funciones:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

El operador de canalización hacia delante y mucho más, se tratan en los tutoriales posteriores.

Esto es sólo un vistazo a lo que puede hacer con F# interactivo.  Para obtener más información, consulte [programación interactiva con F# ](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md), donde abordan algunas de las características principales de la F# lenguaje.  Se le ofrecerá una visión general de algunas de las capacidades de F#y proporcionan ejemplos de código suficiente que puede copiar en Visual Studio para Mac y en ejecución.  También hay algunos excelentes recursos externos, puede usar, exhibió en el [ F# guía](../index.md).

## <a name="see-also"></a>Vea también

- [Visual F#](../index.md)
- [Paseo por F#](../tour.md)
- [F#referencia del lenguaje](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y el operador](../language-reference/symbol-and-operator-reference/index.md)
