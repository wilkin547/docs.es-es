---
title: Introducción a F# en Visual Studio
description: Obtenga información sobre cómo F# usar con Visual Studio.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337344"
---
# <a name="get-started-with-f-in-visual-studio"></a>Introducción a F# en Visual Studio

F#y las herramientas F# visuales se admiten en el entorno de desarrollo integrado (IDE) de Visual Studio.

Para empezar, asegúrese de que tiene [Visual Studio instalado con F# compatibilidad](install-fsharp.md#install-f-with-visual-studio).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

Uno de los proyectos más básicos de Visual Studio es la aplicación de consola. Aquí se muestra cómo crear uno:

1. Abra Visual Studio 2019.

2. En la ventana de inicio, elija **Crear un proyecto nuevo**.

3. En la página **crear un nuevo proyecto** , elija **F#** en la lista idioma.

4. Seleccione la plantilla **aplicación de consola (.net Core)** y, a continuación, elija **siguiente**.

5. En la página **configurar el nuevo proyecto** , escriba un nombre en el cuadro **nombre del proyecto** . Luego, elija **Crear**.

   Visual Studio crea el nuevo F# proyecto. Puede verlo en la ventana Explorador de soluciones.

## <a name="write-the-code"></a>Escribir el código

Comencemos por escribir código. Asegúrese de que el archivo de `Program.fs` está abierto y, a continuación, reemplace el contenido por lo siguiente:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

En el ejemplo de código anterior se define una función llamada `square` que toma una entrada denominada `x` y la multiplica por sí misma. Dado F# que utiliza la [inferencia de tipos](../language-reference/type-inference.md), no es necesario especificar el tipo de `x`. El F# compilador entiende los tipos en los que la multiplicación es válida y asigna un tipo a `x` en función de cómo se llama a `square`. Si mantiene el mouse sobre `square`, debería ver lo siguiente:

```fsharp
val square: x:int -> int
```

Esto es lo que se conoce como la firma de tipo de la función. Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero". El compilador dio `square` el tipo de `int` por ahora; Esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino en un conjunto cerrado de tipos. El F# compilador ajustará la firma de tipo si llama a `square` con un tipo de entrada diferente, como un `float`.

Otra función, `main`, se define, que está decorada con el atributo `EntryPoint`. Este atributo indica al F# compilador que la ejecución del programa debe comenzar allí. Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).

Está en la función de punto de entrada, `main`, que llama a la función de `square` con un argumento de `12`. A F# continuación, el compilador asigna el tipo de `square` que se va a `int -> int` (es decir, una función que toma un `int` y genera un `int`). La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato e imprime el resultado (y una nueva línea). La cadena de formato, similar a los lenguajes de programación de estilo C, tiene parámetros (`%d`) que corresponden a los argumentos que se le pasan, en este caso `12` y `(square 12)`.

## <a name="run-the-code"></a>Ejecución del código

Puede ejecutar el código y ver los resultados presionando **Ctrl**+**F5**. Como alternativa, puede elegir el > de **depurar** **iniciar sin depurar** en la barra de menús de nivel superior. Esto ejecuta el programa sin depuración.

El siguiente resultado se imprime en la ventana de la consola que abrió Visual Studio:

```console
12 squared is: 144!
```

¡Enhorabuena! Ha creado su primer F# proyecto en Visual Studio, ha escrito una F# función que calcula e imprime un valor y ejecuta el proyecto para ver los resultados.

## <a name="next-steps"></a>Pasos siguientes

Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md)por, que cubre algunas de las características principales del F# lenguaje. Proporciona información general sobre algunas de las funcionalidades de F# y ejemplos de código que puede copiar en Visual Studio y ejecutar.

> [!div class="nextstepaction"]
> [Paseo por F](../tour.md)

## <a name="see-also"></a>Vea también

- [F#Referencia del lenguaje](../language-reference/index.md)
- [Inferencia de tipos](../language-reference/type-inference.md)
- [Referencia de símbolos y operadores](../language-reference/symbol-and-operator-reference/index.md)
