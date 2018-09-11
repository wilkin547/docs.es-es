---
title: Parámetros y argumentos (F#)
description: 'Obtenga información sobre la compatibilidad del lenguaje F # para definir parámetros y pasar argumentos a funciones, métodos y propiedades.'
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338264"
---
# <a name="parameters-and-arguments"></a>Parámetros y argumentos

Este tema describe la compatibilidad con lenguajes para definir parámetros y pasar argumentos a funciones, métodos y propiedades. Incluye información acerca de cómo pasar por referencia y cómo definir y usar los métodos que pueden tomar un número variable de argumentos.

## <a name="parameters-and-arguments"></a>Parámetros y argumentos

El término *parámetro* se usa para describir los nombres de los valores que se esperan que se proporcione. El término *argumento* se usa para los valores proporcionados para cada parámetro.

Los parámetros pueden especificarse en la tupla o currificada, o en alguna combinación de ambos. Puede pasar argumentos mediante el uso de un nombre de parámetro explícito. Parámetros de métodos pueden especificarse como opcionales y proporcionado un valor predeterminado.

## <a name="parameter-patterns"></a>Patrones de parámetros

En general, los parámetros proporcionados a las funciones y métodos son patrones separados por espacios. Esto significa que, en principio, cualquiera de los patrones descritos en [expresiones de coincidencia](match-expressions.md) puede usarse en una lista de parámetros para una función o miembro.

Métodos usan normalmente la forma de pasar argumentos de tupla. Dado que la forma de tupla coincide con la forma en que se pasan argumentos en los métodos de .NET se consigue un resultado más claro desde la perspectiva de otros lenguajes. NET.

Currificada más a menudo se usa con funciones creadas con `let` enlaces.

El pseudocódigo siguiente muestra ejemplos de tupla y argumentos currificados.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Combinar ambas formas son posibles cuando algunos argumentos están en tuplas y otros no.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Otros patrones también pueden usarse en las listas de parámetros, pero si el modelo de parámetro no coincide con todas las entradas posibles, podría haber una coincidencia incompleta en tiempo de ejecución. La excepción `MatchFailureException` se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros. El compilador emite una advertencia cuando un modelo de parámetro permite coincidencias incompletas. Al menos otro patrón es suele resultar útil para las listas de parámetros, y ese es el patrón de carácter comodín. Utilice el patrón de caracteres comodín en una lista de parámetros si desea omitir todos los argumentos que se proporcionan. El código siguiente muestra el uso del patrón de carácter comodín en una lista de argumentos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

El carácter comodín puede ser útil cuando no necesite los argumentos pasados, como en el punto de entrada principal a un programa, cuando no esté interesado en los argumentos de línea de comandos que normalmente se proporcionan como una matriz de cadenas, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Otros patrones que a veces se usan argumentos de entrada son el `as` patrón y patrones de identificador asociados a las uniones discriminadas y los patrones activos. Puede usar el modelo de unión discriminada de caso único como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

La salida es la siguiente.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Modelos activos pueden resultar útiles como parámetros, por ejemplo, cuando se transforma un argumento en un formato deseado, como en el ejemplo siguiente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Puede usar el `as` patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Otro patrón que se usa ocasionalmente es una función que deja el último argumento sin nombre proporcionando, como el cuerpo de la función, una expresión lambda que inmediatamente se realiza una coincidencia de patrones en el argumento implícito. Un ejemplo de esto es la siguiente línea de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Este código define una función que toma una lista genérica y devuelve `true` si la lista está vacía, y `false` en caso contrario. El uso de dichas técnicas puede hacer que el código más difícil de leer.

En ocasiones, los patrones que implican coincidencias incompletas son útiles, por ejemplo, si sabe que las listas en el programa tienen solo tres elementos, podría usar un patrón similar al siguiente en una lista de parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

El uso de patrones que tienen coincidencias incompletas mejor está reservado para el desarrollo rápido de prototipos y otros usos temporales. El compilador emitirá una advertencia para dicho código. Estos patrones no pueden cubrir el caso general de todas las entradas posibles y, por tanto, no son adecuados para las API de componentes.

## <a name="named-arguments"></a>Argumentos con nombre

Posición en una lista de argumentos separados por comas se pueden especificar argumentos de métodos o se pueden pasar a un método explícitamente proporcionando el nombre, seguido por un signo igual y el valor que se pasarán en. Si se especifica al proporcionar el nombre, pueden aparecer en un orden diferente del que se utiliza en la declaración.

Argumentos con nombre pueden que el código sea más legible y más adaptable para ciertos tipos de cambios en la API, como la reordenación de parámetros del método.

Argumentos con nombre solo se permiten para los métodos, no para `let`-enlazado funciones, los valores de función o las expresiones lambda.

En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

En una llamada a un constructor de clase, puede establecer los valores de propiedades de la clase utilizando una sintaxis similar a la de argumentos con nombre. El ejemplo siguiente muestra esta sintaxis.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Para obtener más información, consulte [constructores (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parámetros opcionales

Puede especificar un parámetro opcional para un método mediante un signo de interrogación junto al nombre del parámetro. Los parámetros opcionales se interpretan como el tipo de opción de F #, por lo que puede consultar en la que se consultan los tipos de opciones mediante el uso de manera regular un `match` expresión con `Some` y `None`. Los parámetros opcionales solo se permiten en los miembros, no en las funciones creadas mediante `let` enlaces.

También puede usar una función `defaultArg`, que establece un valor predeterminado de un argumento opcional. El `defaultArg` función toma el parámetro opcional como el primer argumento y el valor predeterminado como el segundo.

El ejemplo siguiente muestra el uso de los parámetros opcionales.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

La salida es la siguiente.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Pasar por referencia

Pasar un valor de F # por referencia implica [zkratka](byrefs.md), que son tipos de puntero administrado. Guía para que el tipo debe usar es el siguiente:

* Use `inref<'T>` si solo necesita leer el puntero.
* Use `outref<'T>` si solo tiene que escribir en el puntero.
* Use `byref<'T>` si necesita leer de y escribir en el puntero.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

Dado que el parámetro es un puntero y el valor es mutable, cualquier cambio en el valor se conserva después de la ejecución de la función.

Puede utilizar una tupla como valor devuelto para almacenarlas `out` parámetros en métodos de la biblioteca. NET. Como alternativa, puede tratar el `out` parámetro como un `byref` parámetro. El ejemplo de código siguiente muestra ambas maneras.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrices de parámetros

En ocasiones, es necesario definir una función que toma un número arbitrario de parámetros de tipo heterogéneo. No sería práctico volver a crear todos los métodos sobrecargados posible para tener en cuenta para todos los tipos que se pueda usar. Las implementaciones de .NET proporcionan compatibilidad para dichos métodos a través de la característica de la matriz de parámetros. Con un número arbitrario de parámetros se puede proporcionar un método que toma una matriz de parámetros en la firma. Los parámetros se colocan en una matriz. El tipo de elementos de la matriz determina los tipos de parámetro que se pueden pasar a la función. Si define la matriz de parámetros con `System.Object` como el tipo de elemento, a continuación, el código de cliente puede pasar valores de cualquier tipo.

En F #, las matrices de parámetros solo se pueden definir en métodos. No se usaron en las funciones que se definen en módulos o funciones independientes.

Definir una matriz de parámetros mediante el `ParamArray` atributo. El `ParamArray` atributo solo se puede aplicar al último parámetro.

El código siguiente ilustra la llamada a un método de .NET que toma una matriz de parámetros y la definición de un tipo en F # que tiene un método que toma una matriz de parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Cuando se ejecuta en un proyecto, el resultado del código anterior es como sigue:

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Vea también

- [Miembros](members/index.md)
