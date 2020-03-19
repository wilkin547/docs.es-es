---
title: Parámetros y argumentos
description: Obtenga información sobre la compatibilidad con el lenguaje F para definir parámetros y pasar argumentos a funciones, métodos y propiedades.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401056"
---
# <a name="parameters-and-arguments"></a>Parámetros y argumentos

En este tema se describe la compatibilidad del lenguaje para definir parámetros y pasar argumentos a funciones, métodos y propiedades. Incluye información sobre cómo pasar por referencia y cómo definir y usar métodos que pueden tomar un número variable de argumentos.

## <a name="parameters-and-arguments"></a>Parámetros y argumentos

El *parámetro* term se utiliza para describir los nombres de los valores que se espera que se suminisen. El *término argumento* se utiliza para los valores proporcionados para cada parámetro.

Los parámetros se pueden especificar en forma de tupla o cuajada, o en alguna combinación de los dos. Puede pasar argumentos mediante un nombre de parámetro explícito. Los parámetros de los métodos se pueden especificar como opcionales y se les da un valor predeterminado.

## <a name="parameter-patterns"></a>Patrones de parámetros

Los parámetros proporcionados a funciones y métodos son, en general, patrones separados por espacios. Esto significa que, en principio, cualquiera de los patrones descritos en [Expresiones](match-expressions.md) de coincidencia se puede utilizar en una lista de parámetros para una función o miembro.

Los métodos suelen utilizar la forma de tupla de pasar argumentos. Esto logra un resultado más claro desde la perspectiva de otros lenguajes .NET porque el formulario de tupla coincide con la forma en que se pasan los argumentos en los métodos .NET.

La forma curried se utiliza con `let` mayor frecuencia con funciones creadas mediante enlaces.

El siguiente pseudocódigo muestra ejemplos de tupla y argumentos currudos.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Los formularios combinados son posibles cuando algunos argumentos están en tuplas y otros no.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Otros patrones también se pueden utilizar en las listas de parámetros, pero si el patrón de parámetros no coincide con todas las entradas posibles, puede haber una coincidencia incompleta en tiempo de ejecución. La `MatchFailureException` excepción se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros. El compilador emite una advertencia cuando un patrón de parámetros permite coincidencias incompletas. Al menos otro patrón suele ser útil para las listas de parámetros, y ese es el patrón de comodín. Utilice el patrón de comodín en una lista de parámetros cuando simplemente desee omitir los argumentos que se proporcionan. El código siguiente ilustra el uso del patrón de comodín en una lista de argumentos.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

El patrón de comodín puede ser útil siempre que no necesite los argumentos pasados, como en el punto de entrada principal a un programa, cuando no está interesado en los argumentos de línea de comandos que normalmente se proporcionan como una matriz de cadenas, como en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Otros patrones que a veces se `as` usan en argumentos son el patrón y los patrones de identificador asociados con uniones discriminadas y patrones activos. Puede utilizar el patrón de unión discriminada de un solo caso de la siguiente manera.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

La salida es la siguiente.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Los patrones activos pueden ser útiles como parámetros, por ejemplo, al transformar un argumento en un formato deseado, como en el ejemplo siguiente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Puede usar `as` el patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Otro patrón que se usa ocasionalmente es una función que deja el último argumento sin nombre proporcionando, como el cuerpo de la función, una expresión lambda que realiza inmediatamente una coincidencia de patrón en el argumento implícito. Un ejemplo de esto es la siguiente línea de código.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Este código define una función que `true` toma una lista `false` genérica y devuelve si la lista está vacía y, en caso contrario. El uso de estas técnicas puede hacer que el código sea más difícil de leer.

Ocasionalmente, los patrones que implican coincidencias incompletas son útiles, por ejemplo, si sabe que las listas del programa tienen solo tres elementos, puede usar un patrón como el siguiente en una lista de parámetros.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

El uso de patrones que tienen coincidencias incompletas se reserva mejor para la creación rápida de prototipos y otros usos temporales. El compilador emitirá una advertencia para dicho código. Estos patrones no pueden abarcar el caso general de todas las entradas posibles y, por lo tanto, no son adecuados para las API de componentes.

## <a name="named-arguments"></a>Argumentos con nombre

Los argumentos de los métodos se pueden especificar por posición en una lista de argumentos separados por comas, o se pueden pasar a un método explícitamente proporcionando el nombre, seguido de un signo igual y el valor que se va a pasar. Si se especifica proporcionando el nombre, pueden aparecer en un orden diferente del utilizado en la declaración.

Los argumentos con nombre pueden hacer que el código sea más legible y más adaptable a ciertos tipos de cambios en la API, como un reordenamiento de los parámetros del método.

Los argumentos con nombre solo `let`se permiten para métodos, no para funciones enlazadas, valores de función o expresiones lambda.

En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

En una llamada a un constructor de clase, puede establecer los valores de las propiedades de la clase mediante una sintaxis similar a la de los argumentos con nombre. En el ejemplo siguiente se muestra esta sintaxis.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Para obtener más información, vea [Constructores (F- )](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parámetros opcionales

Puede especificar un parámetro opcional para un método mediante un signo de interrogación delante del nombre del parámetro. Los parámetros opcionales se interpretan como el tipo de opción de F, por lo `match` que `Some` `None`puede consultarlos de la manera regular en que se consultan los tipos de opción, mediante una expresión con y . Los parámetros opcionales solo se permiten `let` en los miembros, no en las funciones creadas mediante enlaces.

Puede pasar valores opcionales existentes al método `?arg=None` `?arg=Some(3)` por `?arg=arg`nombre de parámetro, como o . Esto puede ser útil al compilar un método que pasa argumentos opcionales a otro método.

También puede utilizar `defaultArg`una función, que establece un valor predeterminado de un argumento opcional. La `defaultArg` función toma el parámetro opcional como el primer argumento y el valor predeterminado como el segundo.

En el ejemplo siguiente se muestra el uso de parámetros opcionales.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

La salida es la siguiente.

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

Para los fines de la interoperabilidad de C- y Visual Basic, puede usar los atributos `[<Optional; DefaultParameterValue<(...)>]` en F, de modo que los llamadores verán un argumento como opcional. Esto equivale a definir el argumento como opcional `MyMethod(int i = 3)`en C- como en .

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

También puede especificar un nuevo objeto como valor de parámetro predeterminado. Por ejemplo, `Foo` el miembro `CancellationToken` podría tener un opcional como entrada en su lugar:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

El valor dado `DefaultParameterValue` como argumento para debe coincidir con el tipo del parámetro. Por ejemplo, no se permite lo siguiente:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

En este caso, el compilador genera una advertencia e ignorará ambos atributos por completo. Tenga en cuenta `null` que el valor predeterminado debe anotarse con el tipo, ya que de lo contrario el compilador deduce el tipo incorrecto, es decir, `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.

## <a name="passing-by-reference"></a>Pasando por referencia

Pasar un valor de F por referencia implica [byrefs](byrefs.md), que son tipos de puntero administrado. Las instrucciones para qué tipo utilizar son las siguientes:

- Utilícelo `inref<'T>` si solo necesita leer el puntero.
- Utilícelo `outref<'T>` si solo necesita escribir en el puntero.
- Utilícelo `byref<'T>` si necesita leer y escribir en el puntero.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

Dado que el parámetro es un puntero y el valor es mutable, los cambios en el valor se conservan después de la ejecución de la función.

Puede usar una tupla como valor `out` devuelto para almacenar cualquier parámetro en los métodos de biblioteca de .NET. Como alternativa, puede `out` tratar el `byref` parámetro como un parámetro. En el ejemplo de código siguiente se muestran ambas formas.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrices de parámetros

Ocasionalmente es necesario definir una función que toma un número arbitrario de parámetros de tipo heterogéneo. No sería práctico crear todos los métodos sobrecargados posibles para tener en cuenta todos los tipos que se podrían usar. Las implementaciones de .NET proporcionan compatibilidad con estos métodos a través de la característica de matriz de parámetros. Un método que toma una matriz de parámetros en su firma se puede proporcionar con un número arbitrario de parámetros. Los parámetros se colocan en una matriz. El tipo de los elementos de matriz determina los tipos de parámetro que se pueden pasar a la función. Si define la matriz `System.Object` de parámetros con como el tipo de elemento, el código de cliente puede pasar valores de cualquier tipo.

En F, las matrices de parámetros solo se pueden definir en métodos. No se pueden utilizar en funciones independientes o funciones definidas en módulos.

Defina una matriz de `ParamArray` parámetros mediante el atributo. El `ParamArray` atributo solo se puede aplicar al último parámetro.

En el código siguiente se muestra tanto la llamada a un método .NET que toma una matriz de parámetros como la definición de un tipo en F- que tiene un método que toma una matriz de parámetros.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Cuando se ejecuta en un proyecto, la salida del código anterior es la siguiente:

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Consulte también

- [Miembros](./members/index.md)
