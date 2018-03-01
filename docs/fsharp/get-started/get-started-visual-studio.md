---
title: 'Empezar a trabajar con F # en Visual Studio'
description: "Obtenga información acerca de cómo usar F # con Visual Studio."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 818bf50507a88e1d765da8d0505ed8da4790b71f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-f-in-visual-studio"></a>Empezar a trabajar con F # en Visual Studio

F # y las herramientas de Visual F # se admiten en el IDE de Visual Studio.  Para empezar, debe [descargar Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), si no lo ha hecho ya.  En este artículo usa Visual Studio 2017 Community Edition, pero puede usar F # con la versión de su elección.

## <a name="installing-f"></a>Instalación de F # #

Si va a descargar Visual Studio por primera vez, instalará primero el instalador de Visual Studio.  Instalar cualquier versión de Visual Studio de 2017 desde el instalador. Si ya tiene instalado, haga clic en **modificar**.

A continuación, verá una lista de las cargas de trabajo. Puede instalar F # a través de cualquiera de las cargas de trabajo siguientes:

|Carga de trabajo|Acción|
|--------|------|
| Desarrollo multiplataforma de .NET Core | Ninguna acción - F # se instala de forma predeterminada |
| Desarrollo web y ASP.NET | Ninguna acción - F # se instala de forma predeterminada |
| Desarrollo de Azure | Ninguna acción - F # se instala de forma predeterminada |
| Desarrollo móvil con .NET | Ninguna acción - F # se instala de forma predeterminada |
| Aplicaciones analíticas y de ciencia de datos | Ninguna acción - F # se instala de forma predeterminada |
| Desarrollo de escritorio de .NET | Seleccione **compatibilidad con el escritorio del lenguaje F #** desde el lado derecho |
| Almacenamiento y procesamiento de datos | Seleccione **compatibilidad con el escritorio del lenguaje F #** desde el lado derecho |

A continuación, haga clic en **modificar** en el lado inferior derecho.  Este modo se instalará todo lo que ha seleccionado.  A continuación, puede abrir Visual Studio de 2017 con compatibilidad con el lenguaje F # haciendo clic en **iniciar**.

## <a name="creating-a-console-application"></a>Crear una aplicación de consola

Uno de los proyectos más básicos en Visual Studio es la aplicación de consola.  A continuación le mostramos cómo hacerlo.  Una vez abierto Visual Studio:

1. En el **archivo** menú, elija **New**y, a continuación, elija **proyecto**.

2.  En el icono nuevo proyecto del cuadro de diálogo, en **plantillas**, debería ver **Visual F #**.  Active esta casilla para mostrar las plantillas de F #.

3. Seleccione **.NET principales de aplicación de consola** o **aplicación de consola**.

3. Elija la **bien** botón para crear el proyecto de F #.  Ahora debería ver un proyecto de F # en el Explorador de soluciones.

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

Puede ejecutar el código y ver resultados presionando **ctrl-f5**.  Esto ejecutará el programa sin depurar y le permite ver los resultados.  Como alternativa, puede elegir la **depurar** menú de nivel superior de elementos en Visual Studio y elija **iniciar sin depurar**.

Ahora debería aparecer el siguiente imprime en la ventana de consola que aparecieron Visual Studio:

```
12 squared is 144!
```

¡Enhorabuena!  Ha creado su primer proyecto de F # en Visual Studio, escribe que una función de F # imprime los resultados de la llamada a esa función y ejecute el proyecto para ver algunos resultados.

## <a name="using-f-interactive"></a>Uso de F # Interactive

Una de las mejores características de la Visual F # herramientas en Visual Studio es la ventana interactiva de F #.  Permite enviar código a través a un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.

Para empezar a usarlo, resalte el `square` función definida en el código.  A continuación, mantenga presionada la **Alt** clave y presione **ENTRAR**.  Esto ejecuta el código en la ventana interactiva de F #.  Debe aparecer la ventana interactiva de F # con lo siguiente en él:

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

Los pasos anteriores, define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar. Puede llamar a esta función para ver lo que devuelve con diferentes entradas.  Puede llamar a funciones dentro de las llamadas a funciones:

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

Esto es sólo un vistazo a lo que puede hacer con F # Interactive. Para obtener más información, visite [programación interactiva con F #](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo de F #](../tour.md), donde abordan algunas de las características principales del lenguaje F #.  Se ofrece una visión general de algunas de las capacidades de F # y se proporcionan ejemplos de código de un amplio que puede copiar en Visual Studio y ejecutar.  También hay algunos recursos externos excelentes que puede utilizar, exhibió en el [Guía de F #](../index.md).

## <a name="see-also"></a>Vea también
 [Visual F#](index.md)  
 [Paseo por F](../tour.md)  
 [Referencia del lenguaje F #](../language-reference/index.md)  
 [Inferencia de tipos](../language-reference/type-inference.md)  
 [Referencia de símbolos y el operador](../language-reference/symbol-and-operator-reference/index.md)  
