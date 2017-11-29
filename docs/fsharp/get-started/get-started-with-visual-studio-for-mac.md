---
title: 'Empezar a trabajar con F # en Visual Studio para Mac'
description: "Obtenga información acerca de cómo usar F # con Visual Studio para Mac."
keywords: "visual f#, f#, programación funcional"
author: mizzle-mo
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: beee874e3a549531b520d4ac2150bc10dcab7725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Empezar a trabajar con F # en Visual Studio para Mac

F # y las herramientas de Visual F # se admiten en Visual Studio para Mac IDE.  Para empezar, debe [descargar Visual Studio para Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), si no lo ha hecho ya.  En este artículo usa la 2017 de comunidad de Visual Studio para Mac, pero puede usar F # con la versión de su elección.

## <a name="installing-f"></a>Instalación de F # #

Después de descargar Visual Studio para Mac, le pedirá que elija qué desea instalar.  Para los fines de este artículo se deja los valores predeterminados.  A diferencia de Visual Studio para Windows, no es necesario instalar específicamente la compatibilidad de F #.  Presione "Instalar" para continuar.

Una vez finalizada la instalación, seleccione "Iniciar Visual Studio".  También puede iniciar a través de buscador en macOS.

## <a name="creating-a-console-application"></a>Crear una aplicación de consola

Uno de los proyectos en Visual Studio para Mac más básicos es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez abierto Visual Studio para Mac:

1. En el **archivo** menú, elija **nueva solución**.

2.  En el cuadro de diálogo nuevo proyecto, hay 2 plantillas distintas para la aplicación de consola.  Hay uno en otros -> .NET que tenga como destino .NET Framework.  La otra plantilla es .NET Core -> aplicación destinada a .NET Core.  Cualquier plantilla debería funcionar con el propósito de este artículo.

3. En la aplicación de consola, cambiar C# para F # si es necesario.  Elija la **siguiente** botón para desplazarse hacia delante.  

4. Asigne un nombre al proyecto y elija las opciones que desee para la aplicación.  Observe, el panel de vista previa al lado de la pantalla que muestra la estructura de directorios que se va a crear en función de las opciones seleccionadas.  

5. Haga clic en **Crear**.  Ahora debería ver un proyecto de F # en el Explorador de soluciones.

## <a name="writing-your-code"></a>Escribir el código

Vamos a empezar a escribir código en primer lugar.  Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace el contenido con lo siguiente:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada con el nombre `x` y lo multiplica por sí mismo.  Dado que F # utiliza [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.  El compilador de F # entiende los tipos donde la multiplicación es válida y se asignará un tipo a `x` en función de cómo `square` se llama.  Si mantiene el mouse sobre `square`, debería aparecer lo siguiente:

```
val square: x:int -> int
```

Esto es lo que se conoce como firma de tipo de la función.  Puede leerse como el siguiente: "cuadrado es una función que toma un número entero denominado x y genera un número entero".  Tenga en cuenta que el compilador dio `square` el `int` tipo por ahora - esto es porque no es genérica a través de la multiplicación *todos los* tipos, pero, en su lugar, a través de un conjunto cerrado de tipos, es genérico.  El compilador de F # seleccionado `int` en este punto, pero se ajustará la signatura de tipo si se llama a `square` con otro tipo de entrada, como un `float`.

Otra función, `main`, se define, que se decora con el `EntryPoint` atributo para indicar al compilador de F # ejecución del programa debe empezar por ahí.  Sigue la misma convención que otro [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde los argumentos de línea de comandos se pueden pasar a esta función y se devuelve un código entero (normalmente `0`).

Se encuentra en esta función que se llame a la `square` función con un argumento de `12`.  El compilador de F #, a continuación, asigna el tipo de `square` como `int -> int` (es decir, una función que toma un `int` y genera un `int`).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que corresponden a los indicados en la cadena de formato y, a continuación, se imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución del código

Puede ejecutar el código y ver los resultados, haga clic en **ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.  Esto ejecutará el programa sin depurar y le permite ver los resultados.

Ahora debería aparecer el siguiente imprime en la ventana de consola que aparecieron Visual Studio para Mac:

```
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer proyecto de F # en Visual Studio para Mac, escribe que una función de F # imprime los resultados de la llamada a esa función y ejecute el proyecto para ver algunos resultados.

## <a name="using-f-interactive"></a>Uso de F # Interactive

Una de las mejores características de Visual F # conjunto de herramientas en Visual Studio para Mac es la ventana interactiva de F #.  Permite enviar código a través a un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.

Para empezar a usarlo, resalte el `square` función definida en el código.  A continuación, haga clic en **editar** en el menú de nivel superior.  A continuación seleccione **Enviar selección a F # Interactive**.  Esto ejecuta el código en la ventana interactiva de F #.  Como alternativa, puede haga clic con el botón secundario en la selección y elija **Enviar selección a F # Interactive**.  Debe aparecer la ventana interactiva de F # con lo siguiente en él:

```
>

val square : x:int -> int

>
```

Esto muestra la misma firma de función para el `square` función, que vio anteriormente cuando mantiene el mouse sobre la función.  Dado que `square` es ahora definido en el proceso de F # Interactive, se puede llamar con valores diferentes:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Esto ejecuta la función, se enlaza el resultado a un nuevo nombre `it`y muestra el tipo y el valor de `it`.  Tenga en cuenta que debe finalizar cada línea con `;;`.  Se trata cómo F # Interactive sabe cuando finalice la llamada de función.  También puede definir nuevas funciones en F # Interactive:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Los pasos anteriores, define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar.  Puede llamar a esta función para ver lo que devuelve con diferentes entradas.  Puede llamar a funciones dentro de las llamadas a funciones:

```
> isOdd (square 15);;
val it : bool = true
```

También puede usar el [operador de canalización hacia delante](../language-reference/symbol-and-operator-reference/index.md) debe canalizar el valor en las dos funciones:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

El operador de canalización hacia delante etc., se tratan en los tutoriales posteriores.

Esto es sólo un vistazo a lo que puede hacer con F # Interactive.  Para obtener más información, visite [programación interactiva con F #](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo de F #](../tour.md), donde abordan algunas de las características principales del lenguaje F #.  Se ofrece una visión general de algunas de las capacidades de F # y se proporcionan ejemplos de código de un amplio que puede copiar en Visual Studio para Mac y ejecutar.  También hay algunos recursos externos excelentes que puede utilizar, exhibió en el [Guía de F #](../index.md).

## <a name="see-also"></a>Vea también
 [Visual F#](../index.md)  
 [Paseo por F](../tour.md)  
 [Referencia del lenguaje F #](../language-reference/index.md)  
 [Inferencia de tipos](../language-reference/type-inference.md)  
 [Referencia de símbolos y el operador](../language-reference/symbol-and-operator-reference/index.md)  
