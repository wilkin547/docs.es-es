---
title: Parámetros y argumentos (F#)
description: 'Obtenga información sobre la compatibilidad de idioma de F # para definir parámetros y pasar argumentos a funciones, métodos y propiedades.'
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="parameters-and-arguments"></a>Parámetros y argumentos

Este tema describe la compatibilidad de idioma para definir parámetros y pasar argumentos a funciones, métodos y propiedades. Incluye información sobre cómo pasar por referencia y cómo definir y utilizar métodos que pueden tomar un número variable de argumentos.


## <a name="parameters-and-arguments"></a>Parámetros y argumentos
El término *parámetro* se usa para describir los nombres para los valores que se esperan que se proporcionen. El término *argumento* se usa para los valores proporcionados para cada parámetro.

Pueden especificarse los parámetros en la tupla o formulario currificada o en alguna combinación de los dos. Puede pasar argumentos mediante un nombre de parámetro explícito. Parámetros de métodos pueden especificarse como opcionales y se le asigna un valor predeterminado.


## <a name="parameter-patterns"></a>Modelos de parámetros
En general, los parámetros proporcionados a las funciones y los métodos son modelos separados por espacios. Esto significa que, en principio, cualquiera de los modelos descritos en [expresiones de coincidencia](match-expressions.md) puede utilizarse en una lista de parámetros para una función o un miembro.

Métodos normalmente usan la forma de pasar argumentos tupla. Dado que la forma de tupla coincide con la forma en que se pasan argumentos en los métodos de .NET se obtiene un resultado más claro desde la perspectiva de otros lenguajes. NET.

El formulario currificado se suele utilizar con funciones creadas con `let` enlaces.

El pseudocódigo siguiente muestra ejemplos de tupla y los argumentos currificadas.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Combinar ambas formas son posibles cuando algunos argumentos no son tuplas y otros no.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Otros modelos también se pueden utilizar en listas de parámetros, pero si el patrón de parámetro no coincide con todas las entradas posibles, puede que haya una coincidencia incompleta en tiempo de ejecución. La excepción `MatchFailureException` se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros. El compilador emite una advertencia cuando un modelo de parámetro permite coincidencias incompletas. Al menos otro modelo es suele resultar útil para listas de parámetros y se muestra el patrón de carácter comodín. Usar el patrón de carácter comodín en una lista de parámetros cuando desee pasar por alto los argumentos que se proporcionan. El código siguiente muestra el uso del patrón de carácter comodín en una lista de argumentos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

El patrón de carácter comodín puede ser útil cuando no necesite los argumentos pasados, como en el punto de entrada principal a un programa, cuando no está interesado en los argumentos de línea de comandos que normalmente se proporcionan como una matriz de cadenas, como en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Otros patrones que a veces se usan argumentos de entrada son el `as` patrón y patrones de identificador asociados con uniones discriminadas y modelos activos. Puede usar el modelo de unión discriminada de caso único como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

La salida es la siguiente.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Modelos activos pueden resultar útiles como parámetros, por ejemplo, al transformar un argumento a un formato deseado, como en el ejemplo siguiente:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Puede usar el `as` patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Otro modelo que se usa ocasionalmente es una función que deja el último argumento sin nombre mediante el suministro, como el cuerpo de la función, una expresión lambda que inmediatamente realiza una coincidencia de patrones en el argumento implícito. Un ejemplo de esto es la siguiente línea de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Este código define una función que toma una lista genérica y devuelve `true` si la lista está vacía, y `false` en caso contrario. El uso de estas técnicas puede hacer que el código más difícil de leer.

En ocasiones, los patrones que conllevan coincidencias incompletas resultan útiles, por ejemplo, si sabe que las listas en el programa tienen solo tres elementos, podría usar un patrón similar al siguiente en una lista de parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

El uso de patrones que tengan coincidencias incompletas mejor está reservado para la creación de prototipos rápida y otros usos temporales. El compilador emitirá una advertencia para ese código. Estos patrones no pueden cubrir el caso general de todas las entradas posibles y, por tanto, no son adecuados para las API de componentes.

## <a name="named-arguments"></a>Argumentos con nombre
Posición en una lista de argumentos separados por comas se pueden especificar argumentos para los métodos, o se puede pasar a un método explícitamente proporcionando el nombre, seguido por un signo igual y el valor que se pasará en. Si no especifica al proporcionar el nombre, pueden aparecer en un orden diferente del que se utiliza en la declaración.

Argumentos con nombre pueden que el código sea más legible y más adaptable para ciertos tipos de cambios en la API, como la reordenación de parámetros de método.

Argumentos con nombre se permiten únicamente para los métodos, no para `let`-enlaza las funciones, valores de función o expresiones lambda.

En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

En una llamada a un constructor de clase, puede establecer los valores de propiedades de la clase mediante una sintaxis similar a la de argumentos con nombre. En el ejemplo siguiente se muestra esta sintaxis.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Para obtener más información, consulte [constructores (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Parámetros opcionales
Puede especificar un parámetro opcional para un método mediante un signo de interrogación delante del nombre de parámetro. Parámetros opcionales se interpretan como el tipo de opción de F #, por lo que puede consultar en la manera habitual que se consultan los tipos de opciones mediante el uso de un `match` expresión con `Some` y `None`. Parámetros opcionales solo se permiten en los miembros, no en las funciones creadas mediante `let` enlaces.

También puede usar una función `defaultArg`, que establece un valor predeterminado de un argumento opcional. El `defaultArg` función toma el parámetro opcional como primer argumento y el valor predeterminado como el segundo.

En el ejemplo siguiente se muestra el uso de los parámetros opcionales.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

La salida es la siguiente.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Pasar por referencia
F # admite el `byref` palabra clave, que especifica que un parámetro se pasa por referencia. Esto significa que cualquier cambio en el valor se conserva después de la ejecución de la función. Valores proporcionados a un `byref` parámetro debe ser mutable. Como alternativa, puede pasar las celdas de referencia del tipo adecuado.

Pasar por referencia en los lenguajes .NET ha evolucionado como un modo para devolver más de un valor de una función. En F #, puede devolver una tupla con este fin, o utilizar una celda de referencia mutable como un parámetro. El `byref` parámetro se proporciona principalmente para la interoperabilidad con bibliotecas de. NET.

Los siguientes ejemplos ilustran el uso de la `byref` (palabra clave). Tenga en cuenta que cuando se usa una celda de referencia como un parámetro, debe crear una celda de referencia como un valor con nombre y usarlo como el parámetro, no basta con agregar el `ref` operador tal como se muestra en la primera llamada a `Increment` en el código siguiente. Porque al crear una celda de referencia, crea una copia del valor subyacente, la primera llamada se limita a incrementar un valor temporal.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

Puede utilizar una tupla como valor devuelto para almacenarlas `out` parámetros en métodos de la biblioteca. NET. Como alternativa, puede tratar la `out` parámetro como un `byref` parámetro. En el ejemplo de código siguiente se muestra ambas maneras.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Matrices de parámetros
En ocasiones, es necesario definir una función que toma un número arbitrario de parámetros de tipo heterogéneo. No sería práctico volver a crear todos los métodos sobrecargados posible para tener en cuenta para todos los tipos que se pudieron utilizar. Las implementaciones de .NET proporcionan compatibilidad para dichos métodos a través de la característica de matriz de parámetros. Puede proporcionar un método que toma una matriz de parámetros en la firma con un número arbitrario de parámetros. Los parámetros se colocan en una matriz. El tipo de los elementos de matriz determina los tipos de parámetro que pueden pasarse a la función. Si define la matriz de parámetros con `System.Object` como el tipo de elemento, a continuación, el código de cliente puede pasar valores de cualquier tipo.

En F #, las matrices de parámetros solo pueden definirse en métodos. No se utilizaron en funciones independientes ni en funciones que se definen en módulos.

Definir una matriz de parámetros mediante el `ParamArray` atributo. El `ParamArray` atributo solo se puede aplicar al último parámetro.

El código siguiente muestra llamando a un método de .NET que toma una matriz de parámetros y la definición de un tipo de F # que tiene un método que toma una matriz de parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Cuando se ejecute en un proyecto, el resultado del código anterior es la siguiente:

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Vea también
[Miembros](members/index.md)
