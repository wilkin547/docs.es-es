---
title: Funciones de primera clase
description: 'Obtenga información sobre las funciones de primera clase y cómo son importantes para la programación funcional en F #.'
ms.date: 10/29/2018
ms.openlocfilehash: 1dc8eae1655187282f05bf4e9501ecc8a17deba8
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810916"
---
# <a name="first-class-functions"></a>Funciones de primera clase

Los lenguajes de programación funcional se caracterizan principalmente por tratar las funciones como valores de primera clase. El usuario podrá hacer con las funciones todo lo que se puede hacer con los valores de los otros tipos integrados y, además, con un esfuerzo comparable.

Entre los criterios más comunes para determinar si los valores son de primera clase se encuentran los siguientes:

- ¿Puede enlazar funciones a los identificadores? Es decir, ¿puede asignarles nombres?

- ¿Se pueden almacenar funciones en estructuras de datos, como en una lista?

- ¿Se puede pasar una función como argumento en una llamada de función?

- ¿Se puede devolver una función desde una llamada de función?

Las dos últimas medidas definen lo que se conoce como *operaciones de orden superior* o *funciones de orden superior*. Las funciones de orden superior aceptan otras funciones como argumentos y devuelven funciones como valores de llamadas de función. Estas operaciones son compatibles con los principales pilares de la programación funcional, a saber, las funciones de asignación y la composición de funciones.

## <a name="give-the-value-a-name"></a>Asignar un nombre al valor

Si una función es un valor de primera clase, debe ser posible asignarle un nombre al igual que en el caso de enteros, cadenas y otros tipos integrados. En la programación funcional, esto se denomina "enlazar un identificador a un valor". F # utiliza [ `let` enlaces](../language-reference/functions/let-bindings.md) para enlazar nombres a valores: `let <identifier> = <value>` . En el código siguiente, se muestran dos ejemplos:

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

La asignación de un nombre a una función es así de sencilla. En el ejemplo siguiente se define una función denominada `squareIt` enlazando el identificador `squareIt` a la [expresión lambda](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n` . La función `squareIt` tiene un parámetro, `n`, y devuelve el cuadrado de ese parámetro.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

F# proporciona la siguiente sintaxis más concisa para lograr el mismo resultado.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

En los siguientes ejemplos, se usa principalmente el primer estilo, `let <function-name> = <lambda-expression>`, para recalcar las similitudes entre la declaración de funciones y la declaración de otros tipos de valores. Sin embargo, todas las funciones con nombre también se pueden escribir mediante la sintaxis concisa. Algunos de los ejemplos se han escrito de ambas formas.

## <a name="store-the-value-in-a-data-structure"></a>Almacenar el valor en una estructura de datos

Un valor de primera clase puede almacenarse en una estructura de datos. En el siguiente código, se muestran ejemplos en los se almacenan los valores en listas y tuplas.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

Para comprobar que un nombre de función almacenado en una tupla se evalúa realmente como una función, en el siguiente ejemplo se usan los operadores `fst` y `snd` para extraer los dos primeros elementos de la tupla `funAndArgTuple`. El primer elemento de la tupla es `squareIt` y el segundo elemento es `num`. En un ejemplo anterior, se ha enlazado el identificador `num` al entero 10, un argumento válido para la función `squareIt`. La segunda expresión aplica el primer elemento de la tupla al segundo elemento de la tupla: `squareIt num`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

De forma similar, al igual que en el caso del identificador `num` y el entero 10, el identificador `squareIt` y la expresión lambda `fun n -> n * n` puede usarse indistintamente.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a>Pasar el valor como un argumento

Si un lenguaje trata un valor como un valor de primera clase, se puede pasar dicho valor como argumento de una función. Por ejemplo, los enteros y cadenas se suelen pasar como argumentos. En el siguiente código, se muestran enteros y cadenas que se pasan como argumentos en F#.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

Si una función es un valor de primera clase, dicha función también debe poder pasarse como un argumento. Recuerde que esta es la primera característica de las funciones de orden superior.

En el siguiente ejemplo, la función `applyIt` tiene dos parámetros, `op` y `arg`. Si envía una función con un parámetro a `op` y un argumento apropiado para la función a `arg`, la función devolverá el resultado de aplicar `op` a `arg`. En el siguiente ejemplo, el argumento de función y el argumento entero se envían de la misma manera: por su nombre.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

La capacidad para enviar una función como un argumento a otra función subyace a las abstracciones comunes en los lenguajes de programación funcional, como las operaciones de asignación o de filtrado. Por ejemplo, una operación de asignación es una función de orden superior que captura el cálculo compartido por funciones que recorren una lista, realizan alguna operación con cada elemento y, a continuación, devuelven una lista con los resultados. Quizás se desee incrementar cada elemento de una lista de enteros, elevar cada elemento al cuadrado o cambiar a mayúsculas cada uno de los elementos de una lista de cadenas. La parte del cálculo propensa a errores es el proceso recursivo que recorre la lista y compila una lista de los resultados que se van a devolver. Dicha parte se captura en la función de asignación. Lo único que hay que escribir para una aplicación concreta es la función que se desea aplicar a cada uno de los elementos de la lista (sumar, elevar al cuadrado, cambiar mayúscula a minúscula o viceversa). Dicha función se envía como argumento a la función de asignación, de la misma manera que se envía `squareIt` a `applyIt` en el ejemplo anterior.

F # proporciona métodos de asignación para la mayoría de los tipos de colección, como [listas](../language-reference/lists.md), [matrices](../language-reference/arrays.md)y [secuencias](../language-reference/sequences.md). En los siguientes ejemplos, se utilizan listas. La sintaxis es `List.map <the function> <the list>`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

Para obtener más información, vea [listas](../language-reference/lists.md).

## <a name="return-the-value-from-a-function-call"></a>Devolver el valor de una llamada de función

Por último, si un lenguaje trata una función como valor de primera clase, dicha función debe poder devolverse como valor de una llamada de función, al igual que en el caso de otros tipos como enteros y cadenas.

Las siguientes llamadas de función devuelven enteros y los muestran.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

La siguiente llamada de función devuelve una cadena.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

La siguiente llamada de función, declarada en el propio código, devuelve un valor booleano. El valor mostrado es `True`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

La capacidad para devolver una función como valor de una llamada de función es la segunda característica de las funciones de orden superior. En el siguiente ejemplo, `checkFor` se define como una función que toma un argumento, `item`, y devuelve una nueva función como su valor. La función devuelta toma una lista como argumento, `lst`, y busca `item` en `lst`. Si encuentra `item`, la función devuelve `true`. Si no encuentra `item`, la función devuelve `false`. Como en la sección anterior, el código siguiente usa una función de lista proporcionada [List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists)para buscar en la lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

En el siguiente código, se utiliza `checkFor` para crear una función que toma un argumento (una lista) y busca el número 7 en la lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

En el siguiente ejemplo, se utiliza el estatus de primera clase de las funciones en F# para declarar una función, `compose`, que devuelve una composición de dos argumentos de función.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> Para obtener una versión más corta, vea la siguiente sección, "Funciones currificadas".

En el siguiente código, se envían dos funciones como argumentos a `compose` y las dos toman un solo argumento del mismo tipo. El valor devuelto es una nueva función que es una composición de los dos argumentos de función.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> F# proporciona dos operadores, `<<` y `>>`, que realizan la composición de funciones. Por ejemplo, `let squareAndDouble2 = doubleIt << squareIt` equivale a `let squareAndDouble = compose doubleIt squareIt` del ejemplo anterior.

En el siguiente ejemplo de cómo devolver una función como valor de una llamada de función, se crea un simple juego de adivinanzas. Para crear un juego, llame a `makeGame` y envíe para `target` el valor que el usuario debe adivinar. El valor devuelto de la función `makeGame` es una función que toma un argumento (la adivinanza) y notifica si el usuario ha respondido correctamente a la adivinanza.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

El siguiente código llama a `makeGame`, enviando el valor `7` para `target`. El identificador `playGame` está enlazado a la expresión lambda devuelta. Por consiguiente, `playGame` es una función que toma como único argumento un valor de `guess`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a>Funciones currificadas

Muchos de los ejemplos de la sección anterior se pueden escribir de forma más concisa aprovechando el *currificación* implícito en las declaraciones de función de F #. La currificación es un proceso que consiste en transformar una función con varios parámetros en una serie de funciones incrustadas, cada una de las cuales tiene un solo parámetro. En F#, las funciones con más de un parámetro se currifican de manera inherente. Por ejemplo, la función `compose` que aparece en la sección anterior se puede escribir de manera concisa con tres parámetros, tal y como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

Sin embargo, el resultado es una función con un parámetro que devuelve una función con un parámetro que, a su vez, devuelve otra función con un parámetro, tal y como se muestra en `compose4curried`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

El acceso a esta función puede realizarse de varias maneras. En cada uno de los siguientes ejemplos, se devuelve y se muestra el número 18. Se puede reemplazar `compose4` con `compose4curried` en cualquiera de los ejemplos.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

Para comprobar que la función se ejecuta igual que antes, recurre de nuevo a los casos de prueba originales.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> La currificación se puede restringir agrupando los parámetros en tuplas. Para obtener más información, vea "patrones de parámetro" en [parámetros y argumentos](../language-reference/parameters-and-arguments.md).

En el siguiente ejemplo, se utiliza la currificación implícita para escribir una versión más corta de `makeGame`. Los detalles referentes a cómo `makeGame` construye y devuelve la función `game` son menos explícitos en este formato, pero se pueden usar los casos de prueba originales para comprobar que el resultado es el mismo.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

Para obtener más información sobre currificación, vea "aplicación parcial de argumentos" en [funciones](../language-reference/functions/index.md).

## <a name="identifier-and-function-definition-are-interchangeable"></a>El identificador y la definición de función pueden usarse indistintamente

El nombre de variable `num` de los ejemplos anteriores se evalúa como el entero 10, y no es de extrañar que el entero 10 sea también válido en los casos en los que `num` es válido. Lo mismo se aplica a los identificadores de las funciones y sus valores: siempre que se pueda usar el nombre de la función, se podrá usar la expresión lambda enlazada al mismo.

En el siguiente ejemplo, se define una función `Boolean` denominada `isNegative` y, a continuación, se usan indistintamente el nombre y la definición de la función. En los tres ejemplos siguientes, se devuelve y se muestra `False`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

Para ir incluso un poco más lejos, reemplace `applyIt` por el valor al que está enlazada la función `applyIt`.

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>Las funciones son valores de primera clase en F\#

En los ejemplos que figuran en las secciones anteriores, se muestra que las funciones en F# cumplen los criterios de valores de primera clase:

- Se puede enlazar un identificador a una definición de función.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- Se puede almacenar una función en una estructura de datos.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- Se puede pasar una función como argumento.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- Se puede devolver una función como valor de una llamada de función.
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

Para obtener más información sobre F #, vea la [Referencia del lenguaje f #](../language-reference/index.md).

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

El código siguiente contiene todos los ejemplos de este tema.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a>Consulte también

- [Listas](../language-reference/lists.md)
- [Tuplas](../language-reference/tuples.md)
- [Funciones](../language-reference/functions/index.md)
- [`let` Enlaces](../language-reference/functions/let-bindings.md)
- [Expresiones lambda: `fun` palabra clave](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
