---
title: Introducción a la programación funcional en F#
description: Obtenga información sobre los aspectos básicos de la programación funcional en F#.
ms.date: 10/29/2018
ms.openlocfilehash: 44242a4319a331312a003a555d1483f2a3f1a90d
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110590"
---
# <a name="introduction-to-functional-programming-in-f"></a>Introducción a la programación funcional en F\#

La programación funcional es un estilo de programación que hace hincapié en el uso de funciones y datos inmutables. La programación funcional tipada se da cuando la programación funcional se combina con tipos estáticos, por ejemplo, con F#. En general, en la programación funcional, se insiste en los conceptos siguientes:

* Funciones como construcciones principales empleadas
* Expresiones en lugar de instrucciones
* Valores inmutables frente a variables
* Programación declarativa frente a programación imperativa

A lo largo de esta serie de artículos, explorará los conceptos y los patrones de la programación funcional con F#. Durante el proceso, también aprenderá algo de F#.

## <a name="terminology"></a>Terminología

La programación funcional, al igual que otros paradigmas de programación, incluye un vocabulario que tarde o temprano tendrá que aprender. Estos son algunos de los términos comunes que verá a menudo:

* **Función**: es una construcción que generará una salida cuando se proporcione una entrada. De manera más formal, _asigna_ un elemento de un conjunto a otro. Este formalismo se concreta de muchos modos, sobre todo cuando se usan funciones que operan en colecciones de datos. Es el concepto más básico (e importante) de la programación funcional.
* **Expresión**: se trata de una construcción en el código que genera un valor. En F#, este valor debe estar enlazado u omitirse explícitamente. Una expresión se puede reemplazar de manera trivial por una llamada de función.
* **Pureza**: es una propiedad de una función cuyo valor devuelto siempre es el mismo para los mismos argumentos, y cuya evaluación no tiene efectos secundarios. Una función pura depende completamente de sus argumentos.
* **Transparencia referencial**: se trata de una propiedad de expresiones que se pueden reemplazar por su salida sin que ello afecte al comportamiento de un programa.
* **Inmutabilidad**: significa que un valor no se puede cambiar en contexto. Esto contrasta con las variables, que pueden cambiar en contexto.

## <a name="examples"></a>Ejemplos

Los ejemplos siguientes explican estos conceptos básicos.

### <a name="functions"></a>Functions

En la programación funcional, la construcción más común y fundamental es la función. Esta es una función simple que suma 1 a un entero:

```fsharp
let addOne x = x + 1
```

Su signatura de tipo es la siguiente:

```fsharp
val addOne: x:int -> int
```

La signatura se puede leer como "`addOne` acepta un valor `int` denominado `x` y generará un valor `int`". De manera más formal, `addOne` _asigna_ un valor del conjunto de enteros al conjunto de enteros. El token `->` indica esta asignación. En F#, normalmente puede consultar la signatura de función para tener una idea de lo que hace.

Entonces, ¿por qué es importante la firma? En la programación funcional tipada, la implementación de una función suele ser menos importante que la signatura de tipo real. El hecho de que `addOne` agregue el valor 1 a un entero es interesante en tiempo de ejecución, pero cuando se crea un programa, el hecho de que acepte y devuelva un valor `int` es lo que informa de cómo se usará realmente esta función. Además, una vez que use esta función correctamente (con respecto a su signatura de tipo), el diagnóstico de problemas solo puede realizarse dentro del cuerpo de la función `addOne`. Esta es la motivación que subyace a la programación funcional tipada.

### <a name="expressions"></a>Expresiones

Las expresiones son construcciones que se evalúan como un valor. A diferencia de las instrucciones, que realizan una acción, se puede considerar que las expresiones realizan una acción que devuelve un valor. Las expresiones casi siempre se usan en la programación funcional en lugar de instrucciones.

Considere la función anterior, `addOne`. El cuerpo de `addOne` es una expresión:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Es el resultado de esta expresión lo que define el tipo de resultado de la función `addOne`. Por ejemplo, la expresión que constituye esta función podría cambiarse a un tipo diferente, como `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

Ahora, la signatura de la función es la siguiente:

```fsharp
val addOne: x:'a -> string
```

Dado que en todos los tipos de F# se puede llamar a `ToString()`, el tipo de `x` se ha convertido en genérico (lo que se denomina [generalización automática](../language-reference/generics/automatic-generalization.md)) y el tipo resultante es `string`.

Las expresiones no son solo los cuerpos de las funciones. Puede haber expresiones que generen un valor que se use en otro lugar. Un valor habitual es `if`:

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

La expresión `if` produce un valor denominado `result`. Tenga en cuenta que puede omitir `result` por completo, lo que hace que la expresión `if` sea el cuerpo de la función `addOneIfOdd`. Lo más importante que debe recordar sobre las expresiones es que generan un valor.

Hay un tipo especial, `unit`, que se usa cuando no hay nada que devolver. Por ejemplo, considere esta función simple:

```fsharp
let printString (str: string) =
    printfn $"String is: {str}"
```

El aspecto de la signatura es el siguiente:

```fsharp
val printString: str:string -> unit
```

El tipo `unit` indica que no se devuelve ningún valor real. Esto resulta útil cuando se tiene una rutina que debe "trabajar" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.

Este es un marcado contraste con la programación imperativa, donde la construcción `if` equivalente es una instrucción y la generación de valores se suele realizar con variables mutantes. Por ejemplo, en C#, el código podría escribirse de la manera siguiente:

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

En la programación funcional, es poco habitual mutar valores con instrucciones. Aunque algunos lenguajes funcionales admiten las instrucciones y la mutación, no es habitual usar estos conceptos en la programación funcional.

### <a name="pure-functions"></a>Funciones puras

Como ya se ha mencionado, las funciones puras son aquellas que:

* Siempre se evalúan con el mismo valor para la misma entrada.
* No tienen efectos secundarios.

Resulta útil pensar en las funciones matemáticas en este contexto. En matemáticas, las funciones dependen solo de sus argumentos y no tienen efectos secundarios. En la función matemática `f(x) = x + 1`, el valor de `f(x)` depende solo del valor de `x`. En la programación funcional, las funciones puras son iguales.

Al escribir una función pura, esta debe depender solo de sus argumentos y no realizar ninguna acción que tenga como resultado un efecto secundario.

Este es un ejemplo de una función no pura porque depende de un estado mutable y global:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

La función `addOneToValue` es claramente impura, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1. Este patrón de depender de un valor global debe evitarse en la programación funcional.

Este es otro ejemplo de una función no pura, ya que tiene un efecto secundario:

```fsharp
let addOneToValue x =
    printfn $"x is %d{x}"
    x + 1
```

Aunque esta función no depende de un valor global, escribe el valor de `x` en la salida del programa. Si bien no hay nada intrínsecamente incorrecto, esto significa que la función no es pura. Si otra parte del programa depende de un elemento externo al programa, como el búfer de salida, el hecho de llamar a esta función puede afectar a la otra parte del programa.

La eliminación de la instrucción `printfn` hace que la función sea pura:

```fsharp
let addOneToValue x = x + 1
```

Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con la instrucción `printfn`, garantiza que toda esta función devuelva un valor. La llamada a esta función cualquier número de veces produce el mismo resultado: simplemente genera un valor. La previsibilidad que proporciona la pureza es algo que muchos programadores funcionales se esfuerzan por conseguir.

### <a name="immutability"></a>Inmutabilidad

Por último, uno de los conceptos más básicos de la programación funcional tipada es la inmutabilidad. En F#, todos los valores son inmutables de forma predeterminada. Esto significa que no se pueden mutar en contexto, a menos que los marque explícitamente como mutables.

En la práctica, cuando se trabaja con valores inmutables, el enfoque de la programación pasa de "necesito cambiar algo" a "necesito generar un nuevo valor".

Por ejemplo, si se agrega 1 a un valor, no se muta el valor existente, sino que se genera un nuevo valor:

```fsharp
let value = 1
let secondValue = value + 1
```

En F#, el código siguiente **no** muta la función `value`, sino que realiza una comprobación de igualdad:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Algunos lenguajes de programación funcional no admiten la mutación. En F# se admite, pero no es el comportamiento predeterminado de los valores.

Este concepto también se aplica a las estructuras de datos. En la programación funcional, las estructuras de datos inmutables, como los conjuntos (y muchas más), tienen una implementación diferente de la que cabría esperar inicialmente. Conceptualmente, algo como agregar un elemento a un conjunto no cambia el conjunto, sino que genera un _nuevo_ conjunto con el valor agregado. En segundo plano, esto suele llevarse a cabo mediante una estructura de datos diferente que permite realizar un seguimiento eficaz de un valor, de modo que se pueda proporcionar como resultado la representación adecuada de los datos.

Esta manera de trabajar con valores y estructuras de datos es fundamental, ya que le obliga a tratar cualquier operación que modifique algo como si creara una nueva versión de ese elemento. Esto permite que aspectos como la igualdad y la comparabilidad sean coherentes en los programas.

## <a name="next-steps"></a>Pasos siguientes

En la siguiente sección, se tratarán las funciones en detalle y se explorarán las distintas formas en las que se pueden usar en la programación funcional.

En [Funciones de primera clase](first-class-functions.md) se exploran las funciones en profundidad y se muestra cómo se pueden usar en varios contextos.

## <a name="further-reading"></a>Lecturas adicionales

La serie [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) (Pensar de manera funcional) es otro excelente recurso para obtener información sobre la programación funcional con F#. Trata aspectos básicos de la programación funcional de forma pragmática y fácil de leer y usa características de F# para ilustrar los conceptos.
