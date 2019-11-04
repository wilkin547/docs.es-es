---
title: Introducción a la programación funcional en F#
description: Conozca los aspectos básicos de la programación funcional F#en.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424711"
---
# <a name="introduction-to-functional-programming-in-f"></a>Introducción a la programación funcional en F\#

La programación funcional es un estilo de programación que enfatiza el uso de funciones y datos inmutables. La programación funcional con tipo es cuando la programación funcional se combina con tipos estáticos, F#como con. En general, los conceptos siguientes se destacan en la programación funcional:

* Funciona como construcciones principales que se usan
* Expresiones en lugar de instrucciones
* Valores inmutables en variables
* Programación declarativa a través de la programación imperativa

A lo largo de esta serie, explorará conceptos y patrones en la F#programación funcional con. A lo largo del proceso, también aprenderá algunas F# .

## <a name="terminology"></a>Terminología

La programación funcional, al igual que otros paradigmas de programación, incluye un vocabulario que finalmente tendrá que aprender. Estos son algunos de los términos comunes que verá todo el tiempo:

* **Función** : una función es una construcción que generará una salida cuando se proporcione una entrada. Más formalmente, _asigna_ un elemento de un conjunto a otro conjunto. Este formalismo se eleva en concreto de muchas maneras, especialmente cuando se usan funciones que operan en colecciones de datos. Es el concepto más básico (y importante) de la programación funcional.
* **Expresión** : una expresión es una construcción de código que genera un valor. En F#, este valor debe estar enlazado o omitirse explícitamente. Una expresión se puede reemplazar trivialmente por una llamada de función.
* **La pureza-pureza** es una propiedad de una función de modo que el valor devuelto sea siempre el mismo para los mismos argumentos, y que su evaluación no tenga efectos secundarios. Una función pura depende completamente de sus argumentos.
* **Transparencia referencial** : la transparencia referencial es una propiedad de expresiones de modo que se pueden reemplazar por su salida sin afectar al comportamiento de un programa.
* **Inmutabilidad** : la inmutabilidad significa que un valor no se puede cambiar en contexto. Esto contrasta con las variables, que pueden cambiar en su lugar.

## <a name="examples"></a>Ejemplos

En los siguientes ejemplos se muestran estos conceptos básicos.

### <a name="functions"></a>Funciones

La construcción más común y fundamental en la programación funcional es la función. Esta es una función simple que suma 1 a un entero:

```fsharp
let addOne x = x + 1
```

Su signatura de tipo es la siguiente:

```fsharp
val addOne: x:int -> int
```

La firma se puede leer como "`addOne` acepta un `int` denominado `x` y generará una `int`". Más formalmente, `addOne` está _asignando_ un valor del conjunto de enteros al conjunto de enteros. El token `->` significa esta asignación. En F#, normalmente puede ver la firma de la función para obtener una idea de lo que hace.

Por lo tanto, ¿por qué es importante la firma? En la programación funcional con tipo, la implementación de una función suele ser menos importante que la firma de tipo real. El hecho de que `addOne` agregue el valor 1 a un entero es interesante en tiempo de ejecución, pero cuando se crea un programa, el hecho de que acepte y devuelva un `int` es lo que informa de cómo se utilizará realmente esta función. Además, una vez que use esta función correctamente (con respecto a su firma de tipo), el diagnóstico de cualquier problema solo puede realizarse dentro del cuerpo de la función `addOne`. Este es el estímulo detrás de la programación funcional con tipo.

### <a name="expressions"></a>Expresiones

Las expresiones son construcciones que se evalúan como un valor. A diferencia de las instrucciones, que realizan una acción, se pueden considerar expresiones al realizar una acción que devuelve un valor. Las expresiones casi siempre se usan en favor de instrucciones en la programación funcional.

Considere la función anterior, `addOne`. El cuerpo de `addOne` es una expresión:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Es el resultado de esta expresión que define el tipo de resultado de la función `addOne`. Por ejemplo, la expresión que constituye esta función podría cambiarse para ser un tipo diferente, como una `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

La firma de la función es ahora:

```fsharp
val addOne: x:'a -> string
```

Dado que cualquier tipo F# de puede tener `ToString()` llama a en él, el tipo de `x` se ha convertido en genérico (denominado [generalización automática](../language-reference/generics/automatic-generalization.md)) y el tipo resultante es una `string`.

Las expresiones no son solo los cuerpos de las funciones. Puede tener expresiones que generen un valor que se utilice en otro lugar. Una común es `if`:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

La expresión `if` produce un valor denominado `result`. Tenga en cuenta que puede omitir `result` por completo, lo que hace que la expresión de `if` sea el cuerpo de la función `addOneIfOdd`. Lo más importante que debe recordar sobre las expresiones es que generan un valor.

Hay un tipo especial, `unit`, que se usa cuando no hay nada que devolver. Por ejemplo, considere esta función simple:

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

La firma tiene el siguiente aspecto:

```fsharp
val printString: str:string -> unit
```

El tipo de `unit` indica que no se devuelve ningún valor real. Esto resulta útil cuando se tiene una rutina que debe "trabajar" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.

Esto está en contraste con la programación imperativa, donde la construcción de `if` equivalente es una instrucción, y la generación de valores se suele realizar con variables mutantes. Por ejemplo, en C#, el código podría escribirse de la siguiente manera:

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

Merece la pena mencionar que C# y otros lenguajes de estilo C admiten la [expresión ternaria](../../csharp/language-reference/operators/conditional-operator.md), que permite la programación condicional basada en expresiones.

En la programación funcional, es poco habitual mutar los valores con las instrucciones. Aunque algunos lenguajes funcionales admiten instrucciones y mutación, no es habitual utilizar estos conceptos en la programación funcional.

### <a name="pure-functions"></a>Funciones puras

Como se mencionó anteriormente, las funciones puras son funciones que:

* Siempre se evalúan con el mismo valor para la misma entrada.
* No tener efectos secundarios.

Resulta útil pensar en las funciones matemáticas en este contexto. En las matemáticas, las funciones dependen solo de sus argumentos y no tienen efectos secundarios. En la función matemática `f(x) = x + 1`, el valor de `f(x)` depende solo del valor de `x`. Las funciones puras en la programación funcional son la misma manera.

Al escribir una función pura, la función debe depender solo de sus argumentos y no realizar ninguna acción que tenga como resultado un efecto secundario.

Este es un ejemplo de una función no pura porque depende del estado global y mutable:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

La función `addOneToValue` es claramente inpura, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1. Este patrón de en función de un valor global se debe evitar en la programación funcional.

Este es otro ejemplo de una función no pura, ya que realiza un efecto secundario:

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

Aunque esta función no depende de un valor global, escribe el valor de `x` en la salida del programa. Aunque no hay nada inherentemente incorrecto, esto significa que la función no es pura. Si otra parte del programa depende de algo externo al programa, como el búfer de salida, llamar a esta función puede afectar a la otra parte del programa.

La eliminación de la instrucción `printfn` hace que la función sea pura:

```fsharp
let addOneToValue x = x + 1
```

Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con la instrucción `printfn`, garantiza que toda esta función devuelve un valor. Llamar a esta función cualquier número de veces produce el mismo resultado: simplemente genera un valor. La capacidad de previsión proporcionada por la pureza es algo que los programadores funcionales están procurando.

### <a name="immutability"></a>Inmutabilidad

Por último, uno de los conceptos fundamentales de la programación funcional con tipo es la inmutabilidad. En F#, todos los valores son inmutables de forma predeterminada. Esto significa que no se pueden mutar en contexto a menos que los marque explícitamente como mutables.

En la práctica, el trabajo con valores inmutables significa que se cambia el enfoque a la programación de, "es necesario cambiar algo", a "es necesario generar un nuevo valor".

Por ejemplo, si se agrega 1 a un valor, se genera un nuevo valor, no se modifica el existente:

```fsharp
let value = 1
let secondValue = value + 1
```

En F#, el código siguiente **no** muta la función `value`; en su lugar, realiza una comprobación de igualdad:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Algunos lenguajes de programación funcionales no admiten la mutación. En F#, es compatible, pero no es el comportamiento predeterminado de los valores de.

Este concepto se extiende aún más a las estructuras de datos. En la programación funcional, las estructuras de datos inmutables como los conjuntos (y muchos más) tienen una implementación diferente de la que cabría esperar inicialmente. Conceptualmente, algo como agregar un elemento a un conjunto no cambia el conjunto, genera un _nuevo_ conjunto con el valor agregado. En segundo plano, esto se logra con una estructura de datos diferente que permite realizar un seguimiento eficaz de un valor para que se pueda proporcionar como resultado la representación adecuada de los datos.

Este estilo de trabajo con valores y estructuras de datos es fundamental, ya que le obliga a tratar cualquier operación que modifique algo como si creara una nueva versión de ese elemento. Esto permite que elementos como la igualdad y la comparación sean coherentes en los programas.

## <a name="next-steps"></a>Pasos siguientes

En la siguiente sección, se tratarán detalladamente las funciones y se explorarán las distintas formas en que se pueden usar en la programación funcional.

[Las funciones de primera clase](first-class-functions.md) exploran las funciones en profundidad, lo que muestra cómo se pueden usar en varios contextos.

## <a name="further-reading"></a>Información adicional

La serie [funcionalmente](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) es otro recurso fantástico para obtener información sobre la programación funcional F#con. Trata aspectos básicos de la programación funcional de forma pragmática y fácil de leer, mediante el uso F# de características para ilustrar los conceptos.
