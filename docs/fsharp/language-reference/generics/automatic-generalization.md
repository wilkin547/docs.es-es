---
title: Generalización automática (F#)
description: 'Obtenga información acerca de cómo F # generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9b599fd9fe1220b41987bc14a420ed5740aa05f5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="automatic-generalization"></a>Generalización automática

F # utiliza la inferencia para evaluar los tipos de funciones y expresiones. Este tema describe cómo F # generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.


## <a name="automatic-generalization"></a>Generalización automática
El compilador de F #, mientras se realiza la inferencia de tipo en una función, determina si un parámetro determinado puede ser genérico. El compilador examina cada parámetro y determina si la función tiene una dependencia en el tipo específico de ese parámetro. Si no es así, el tipo se deduce para ser genérico.

En el ejemplo de código siguiente se muestra una función que el compilador deduce para ser genérico.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

El tipo se deduce como `'a -> 'a -> 'a`.

El tipo indica que se trata de una función que toma dos argumentos del mismo tipo desconocido y devuelve un valor de ese mismo tipo. Uno de los motivos que la función anterior puede ser genérica es que el mayor-que (operador) (`>`) es genérico. La mayor-de operador tiene la firma `'a -> 'a -> bool`. No todos los operadores son genéricos, y si el código de una función usa un tipo de parámetro junto con un operador o función no genérica, no se puede generalizar ese tipo de parámetro.

Dado que `max` es genérico, se puede utilizar con tipos como `int`, `float`, y así sucesivamente, tal como se muestra en los ejemplos siguientes.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Sin embargo, los dos argumentos deben ser del mismo tipo. La firma es `'a -> 'a -> 'a`, no `'a -> 'b -> 'a`. Por lo tanto, el código siguiente genera un error porque los tipos no coinciden.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

El `max` función también funciona con cualquier tipo que admita la mayor-que el operador. Por lo tanto, se puede también usarla en una cadena, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a>Restricción de valor
El compilador realiza la generalización automática sólo en las definiciones de función completa que tienen argumentos explícitos y en valores inmutables simples.

Esto significa que el compilador emite un error si intenta compilar el código que no es lo suficientemente restringirse para que sea un tipo específico, pero también no es generalizable. El mensaje de error para este problema se refiere a esta restricción de la generalización automática para los valores como el *valor restricción*.

Normalmente, se produce el error de restricción de valor cuando se desea una construcción sea genérica pero el compilador tiene información suficiente para generalizarla, o cuando se omite involuntariamente suficiente información de tipo en una construcción no genérica. La solución para el error de restricción de valor es proporcionar información más explícita para limitar detalla el problema de inferencia de tipo en una de las maneras siguientes:


- Restringir un tipo para que no sea genérico agregando una anotación de tipo explícita a un valor o parámetro.

- Si el problema está usando una construcción no generalizable para definir una función genérica, como una composición de funciones o argumentos de funciones currificadas no se han aplicado, intente volver a escribir la función como una definición de función ordinaria.

- Si el problema es una expresión que es demasiado compleja para generalizarla, conviértala en una función mediante la adición de un parámetro adicional no utilizado.

- Agregar parámetros de tipo genérico explícitos. Esta opción se usa con poca frecuencia.

- Los ejemplos de código siguiente muestran cada uno de estos escenarios.

Caso 1: Expresión demasiado compleja. En este ejemplo, la lista `counter` está diseñada para ser `int option ref`, pero no está definido como un valor inmutable simple.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Caso 2: Uso de una construcción no generalizable para definir una función genérica. En este ejemplo, la construcción es no generalizable porque implica la aplicación parcial de argumentos de función.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Caso 3: Agregar un parámetro adicional no utilizado. Dado que esta expresión no es lo suficientemente sencilla para la generalización, el compilador emite el error de restricción de valor.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Caso 4: Agregar los parámetros de tipo.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

En el último caso, el valor se convierte en una función de tipo, que puede utilizarse para crear valores de muchos tipos diferentes, por ejemplo como se indica a continuación:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Vea también
[Inferencia de tipos](../type-inference.md)

[Genéricos](index.md)

[Parámetros de tipo resueltos estáticamente](statically-resolved-type-parameters.md)

[Restricciones](constraints.md)

