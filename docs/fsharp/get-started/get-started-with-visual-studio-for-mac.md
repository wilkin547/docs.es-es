---
title: 'Introducción a F # en Visual Studio para Mac'
description: 'Obtenga información sobre cómo usar F # con Visual Studio para Mac.'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437987"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Introducción a F # en Visual Studio para Mac

F # y las herramientas de Visual F# se admiten en el IDE de Visual Studio para Mac. Asegúrese de que ha [instalado Visual Studio para Mac](install-fsharp.md#install-f-with-visual-studio-for-mac).

## <a name="creating-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos más básicos de Visual Studio para Mac es la aplicación de consola.  Aquí se muestra cómo hacerlo.  Una vez que Visual Studio para Mac está abierto:

1. En el menú **archivo** , elija **nueva solución**.

2. En el cuadro de diálogo nuevo proyecto, hay dos plantillas diferentes para la aplicación de consola.  Hay una en otras > .NET que tiene como destino el .NET Framework.  La otra plantilla está en .NET Core-> aplicación que tiene como destino .NET Core.  Cualquier plantilla debe funcionar para este artículo.

3. En aplicación de consola, cambie C# a F # si es necesario.  Elija el botón **siguiente** para avanzar.  

4. Asigne un nombre al proyecto y elija las opciones que quiera para la aplicación.  Fíjese en el panel de vista previa en el lateral de la pantalla que mostrará la estructura de directorios que se creará en función de las opciones seleccionadas.  

5. Haga clic en **Crear**.  Ahora debería ver un proyecto de F # en el Explorador de soluciones.

## <a name="writing-your-code"></a>Escritura del código

Vamos a empezar por escribir código primero.  Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace el contenido por lo siguiente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior, se ha definido una función `square` que toma una entrada denominada `x` y la multiplica por sí misma.  Dado que F # usa la [inferencia de tipos](../language-reference/type-inference.md), `x` no es necesario especificar el tipo de.  El compilador de F # entiende los tipos en los que la multiplicación es válida y asignará un tipo a `x` basándose en cómo `square` se llama a.  Si mantiene el puntero sobre `square` , debería ver lo siguiente:

```console
val square: x:int -> int
```

Esto es lo que se conoce como la firma de tipo de la función.  Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero".  Tenga en cuenta que el compilador dio `square` el `int` tipo por ahora: esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino que es genérica en un conjunto cerrado de tipos.  El compilador de F # eligió `int` en este punto, pero ajustará la firma del tipo si llama `square` a con otro tipo de entrada, como `float` .

Otra función, `main` , se define, que se decora con el `EntryPoint` atributo para indicar al compilador de F # que la ejecución del programa debe comenzar allí.  Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0` ).

En esta función se llama a la `square` función con un argumento de `12` .  A continuación, el compilador de F # asigna el tipo de `square` a `int -> int` (es decir, una función que toma `int` y produce `int` ).  La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que se corresponden con los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.

## <a name="running-your-code"></a>Ejecución de código

Puede ejecutar el código y ver los resultados haciendo clic en **Ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.  Así se ejecutará el programa sin depurar y podrá ver los resultados.

Ahora debería ver lo siguiente impreso en la ventana de la consola que Visual Studio para Mac emerge:

```console
12 squared is 144!
```

Enhorabuena.  Ha creado su primer proyecto de F # en Visual Studio para Mac, ha escrito una función de F # y ha impreso los resultados de una llamada a esa función, y ejecuta el proyecto para ver algunos resultados.

## <a name="using-f-interactive"></a>Usar F# interactivo

Una de las mejores características de las herramientas de Visual F# en Visual Studio para Mac es la ventana de F# interactivo.  Permite enviar código a un proceso en el que se puede llamar a ese código y ver el resultado de forma interactiva.

Para empezar a usarlo, resalte la `square` función definida en el código.  A continuación, haga clic en **Editar** en el menú de nivel superior.  A continuación, seleccione **Enviar selección a F# interactivo**.  Esto ejecuta el código en la ventana F# interactivo.  Como alternativa, puede hacer clic con el botón derecho en la selección y elegir **Enviar selección a F# interactivo**.  Debería ver que la ventana de F# interactivo aparece con lo siguiente en ella:

```console
>

val square : x:int -> int

>
```

Esto muestra la misma firma de función para la `square` función, que vio anteriormente al mantener el mouse sobre la función.  Dado `square` que ahora se define en el proceso de F# interactivo, puede llamarlo con valores diferentes:

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

De esta forma, se ejecuta la función, se enlaza el resultado a un nuevo nombre `it` y se muestra el tipo y el valor de `it` .  Tenga en cuenta que debe terminar cada línea con `;;` .  Así es como F# interactivo sabe cuándo finaliza la llamada de función.  También puede definir nuevas funciones en F# interactivo:

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Lo anterior define una nueva función, `isOdd` , que toma `int` y comprueba si es impar.  Puede llamar a esta función para ver lo que devuelve con diferentes entradas.  Puede llamar a funciones dentro de las llamadas de función:

```console
> isOdd (square 15);;
val it : bool = true
```

También puede usar el [operador de canalización directa](../language-reference/symbol-and-operator-reference/index.md) para canalizar el valor en las dos funciones:

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

El operador de canalización hacia delante, y más, se trata en los tutoriales posteriores.

Esto solo es un vistazo a lo que puede hacer con F# interactivo.  Para obtener más información, consulte [programación interactiva con F #](../tools/fsharp-interactive/index.md).

## <a name="next-steps"></a>Pasos siguientes

Si todavía no lo ha hecho, consulte el [paseo por f #](../tour.md), que trata algunas de las características principales del lenguaje f #.  Le proporcionará una visión general de algunas de las funcionalidades de F # y proporcionará ejemplos de código que puede copiar en Visual Studio para Mac y ejecutar.  También hay algunos excelentes recursos externos que puede usar, que se muestran en la [Guía de F #](../index.yml).

## <a name="see-also"></a>Consulte también

- [Guía de F#](../index.yml)
- [Paseo por F#](../tour.md)
- [Referencia del lenguaje F#](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y operadores](../language-reference/symbol-and-operator-reference/index.md)
