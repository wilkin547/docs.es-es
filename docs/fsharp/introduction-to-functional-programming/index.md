---
title: Introducción a la programación funcional en F#
description: Conozca los aspectos básicos de la programación funcional en F#.
ms.date: 10/29/2018
ms.openlocfilehash: 84022e58c0f17b9e9875402c653c31e494e940da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772793"
---
# <a name="introduction-to-functional-programming-in-f"></a>Introducción a la programación funcional en F\#

Programación funcional es un estilo de programación que resalta el uso de funciones y datos inmutables. Programación funcional con tipo es cuando se combina la programación funcional con tipos estáticos, como con F#. En general, se destacan los siguientes conceptos de programación funcional:

* Funciones como las construcciones principales que usar
* Expresiones en lugar de instrucciones
* Valores inmutables sobre las variables
* Programación declarativa a través de la programación imperativa

A lo largo de esta serie, exploraremos los conceptos y patrones de programación funcional mediante F#. En el camino, obtendrá información sobre algunos F# demasiado.

## <a name="terminology"></a>Terminología

Incluye un vocabulario que finalmente deberá aprender programación funcional, al igual que otros paradigmas de programación. Estos son algunos términos comunes que verá todo el tiempo:

* **Función** -una función es una construcción que generará un resultado cuando se especifica una entrada. Más formalmente, lo _asigna_ establece un elemento de uno a otro conjunto. Este formalismo se levanta en lo concreto en muchos sentidos, especialmente cuando se usa funciones que operan en colecciones de datos. Es un concepto más básico (e importante) en la programación funcional. 
* **Expresión** : una expresión es una construcción de código que genera un valor. En F#, este valor debe ser enlazada o explícitamente se omiten. Una expresión se puede reemplazar de forma trivial mediante una llamada de función.
* **Pureza** -pureza es una propiedad de una función de modo que su valor devuelto siempre es el mismo para los mismos argumentos, y que su evaluación tiene efectos secundarios. Una función pura depende por completo sus argumentos.
* **Transparencia referencial** -transparencia referencial es una propiedad de las expresiones de modo que puedan reemplazarse con sus resultados sin afectar al comportamiento de un programa.
* **La inmutabilidad** -significa de inmutabilidad que no puede ser un valor cambiado en contexto. Se trata a diferencia de las variables, que pueden cambiar en su lugar.

## <a name="examples"></a>Ejemplos

Los ejemplos siguientes muestran estos conceptos básicos.

### <a name="functions"></a>Funciones

Una construcción más comunes y fundamental en la programación funcional es la función. Esta es una función sencilla que suma 1 a un entero:

```fsharp
let addOne x = x + 1
```

La firma de su tipo es como sigue:

```fsharp
val addOne: x:int -> int
```

La firma se puede leer como, "`addOne` acepta un `int` denominado `x` y generará una `int`". Más formalmente, `addOne` es _asignación_ un valor del conjunto de enteros para el conjunto de enteros. El `->` token significa que esta asignación. En F#, normalmente puede mirar la firma de función para hacerse una idea de lo que hace.

Por lo tanto, ¿por qué la firma es importante? En la programación funcional con tipo, la implementación de una función suele ser más importante que la firma del tipo real. El hecho de que `addOne` agrega el valor 1 en un entero es interesante en tiempo de ejecución, pero cuando se construye un programa, el hecho de que acepte y devuelva un `int` es lo que le informa de cómo lo utilizará esta función. Además, una vez que use esta función correctamente (con respecto a su signatura de tipo), diagnosticar problemas puede realizarse solo dentro del cuerpo de la `addOne` función. Este es el impulso que hay detrás de la programación funcional con tipo.

### <a name="expressions"></a>Expresiones

Las expresiones son construcciones que se evalúan como un valor. A diferencia de las instrucciones, que realizan una acción, se pueden considerar las expresiones de llevar a cabo una acción que devuelve un valor. Las expresiones se usan casi siempre en favor de las instrucciones en la programación funcional.

Considere la función anterior, `addOne`. El cuerpo de `addOne` es una expresión:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Es el resultado de esta expresión que define el tipo de resultado de la `addOne` función. Por ejemplo, se pudo cambiar la expresión que constituye esta función para que sea un tipo diferente, como un `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

La firma de la función ahora es:

```fsharp
val addOne: x:'a -> string
```

Desde cualquier tipo de F# puede tener `ToString()` llamado en ella, el tipo de `x` se ha realizado genérico (llamado [generalización automática](../language-reference/generics/automatic-generalization.md)), y el tipo resultante es un `string`.

Las expresiones no son simplemente los cuerpos de funciones. Puede hacer que las expresiones que producen un valor que se usa en otro lugar. Es un común `if`:

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

El `if` expresión genera un valor denominado `result`. Tenga en cuenta que puede omitir `result` por completo, que hace el `if` el cuerpo de la expresión de la `addOneIfOdd` función. La clave que debe recordar acerca de las expresiones es que genera un valor.

Hay un tipo especial, `unit`, que se utiliza cuando hay que devolver nada. Por ejemplo, considere la posibilidad de esta función simple:

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

La firma tiene este aspecto:

```fsharp
val printString: str:string -> unit
```

El `unit` tipo indica que no hay ningún valor real que se devuelve. Esto es útil cuando tiene una rutina que debe "funcione" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.

Esto es en contraste con la programación imperativa, donde el equivalente `if` construcción es una instrucción y generar los valores se suele hacer con las variables de mutación. Por ejemplo, en C#, se podría escribir el código similar al siguiente:

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

Merece la pena mencionar que C# y otros lenguajes de estilo de C admiten la [expresión ternaria](../../csharp/language-reference/operators/conditional-operator.md), lo que permite la programación condicional basada en expresión.

En la programación funcional, es poco frecuente mutar valores con instrucciones. Aunque algunos lenguajes funcionales son compatibles con las instrucciones y mutación, no es habitual usar estos conceptos en la programación funcional.

### <a name="pure-functions"></a>Funciones puras

Como se mencionó anteriormente, puras funciones son funciones:

* Evalúe siempre el mismo valor para la misma entrada.
* No tienen efectos secundarios.

Resulta útil pensar en las funciones matemáticas en este contexto. En matemáticas, las funciones sólo dependen de sus argumentos y no tiene efectos secundarios. En la función matemática `f(x) = x + 1`, el valor de `f(x)` solo depende del valor de `x`. Las funciones puras en la programación funcional son la misma manera.

Al escribir una función pura, la función debe depender únicamente de sus argumentos y no realiza ninguna acción que da como resultado un efecto secundario.

Este es un ejemplo de una función no pura porque depende de estado mutable global:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

El `addOneToValue` función es claramente impuras, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1. Este patrón de según un valor global es que deben evitarse en la programación funcional.

Este es otro ejemplo de una función no pura, ya que realiza un efecto secundario:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

Aunque esta función no depende de un valor global, escribe el valor de `x` a la salida del programa. Aunque no hay ningún problema inherente al hacer esto, ¿significa que la función no es pura. Si otra parte del programa depende de algo externo para el programa, como el búfer de salida, a continuación, llamar a esta función puede afectar a otra parte del programa.

Quitar el `printfn` instrucción hace que la función pura:

```fsharp
let addOneToValue x = x + 1
```

Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con el `printfn` instrucción, garantizar que todo lo que hace esta función es devolver un valor. Llamar a esta función en cualquier número de veces que produce el mismo resultado: solo genera un valor. La capacidad de predicción dado por la pureza es algo que muchos programadores funcionales se esfuerzan por lograr.

### <a name="immutability"></a>Inmutabilidad

Por último, uno de los conceptos más fundamentales de la programación funcional con tipo es la inmutabilidad. En F#, todos los valores son inmutables de manera predeterminada. Esto significa que no pueden ser transformarlos in situ a menos que marque explícitamente como mutables.

En la práctica, trabajar con valores inmutables significa que cambiar su enfoque a la programación de "Necesito cambiar algo" a "necesito generar un nuevo valor".

Por ejemplo, agregando 1 a un valor significa que generar un nuevo valor, no una mutación existente:

```fsharp
let value = 1
let secondValue = value + 1
```

En F#, el código siguiente hace **no** mutar la `value` función; en su lugar, realiza una comprobación de igualdad:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Algunos lenguajes de programación funcionales no admiten mutación en absoluto. En F#, que es compatible, pero no es el comportamiento predeterminado para los valores.

Este concepto se extiende más allá de las estructuras de datos. En la programación funcional, estructuras de datos inmutables como conjuntos (y muchos más) tienen una implementación diferente que inicialmente podría esperan. Conceptualmente, algo así agregando un elemento a un conjunto no cambia el conjunto, genera un _nuevo_ establecido con el valor agregado. En segundo plano, a menudo esto se logra mediante una estructura de datos diferentes que se permite para el seguimiento de forma eficaz un valor para que la representación apropiada de los datos puede tener como resultado.

Este estilo de trabajar con los valores y las estructuras de datos es fundamental, tal como nos vemos obligados a tratar cualquier operación que modifique algo como si crea una nueva versión de eso. Esto permite cosas como comprobar su igualdad y comparación para que sea coherente en los programas.

## <a name="next-steps"></a>Pasos siguientes

La siguiente sección tratará exhaustivamente las funciones, explorar maneras diferentes, puede usar en la programación funcional.

[Funciones de primera clase](first-class-functions.md) explora funciones profundamente, que muestra cómo puede usarlos en distintos contextos.

## <a name="further-reading"></a>Información adicional

El [funcionalmente pensando](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) serie es otro excelente recurso para aprender sobre la programación funcional con F#. Abarca conceptos básicos de la programación funcional de forma pragmática y fácil de leer, con F# características para ilustrar los conceptos.
