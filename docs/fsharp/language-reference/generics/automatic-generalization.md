---
title: Generalización automática
description: Obtenga información F# acerca de cómo generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630627"
---
# <a name="automatic-generalization"></a>Generalización automática

F#utiliza la inferencia de tipos para evaluar los tipos de funciones y expresiones. En este tema se F# describe cómo generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.

## <a name="automatic-generalization"></a>Generalización automática

El F# compilador, cuando realiza la inferencia de tipos en una función, determina si un parámetro determinado puede ser genérico. El compilador examina cada parámetro y determina si la función tiene una dependencia en el tipo específico de ese parámetro. Si no es así, se deduce que el tipo es genérico.

En el ejemplo de código siguiente se muestra una función que el compilador deduce que es genérica.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

El tipo se deduce como `'a -> 'a -> 'a`.

El tipo indica que se trata de una función que toma dos argumentos del mismo tipo desconocido y devuelve un valor del mismo tipo. Uno de los motivos por los que la función anterior puede ser genérico es que el operador "mayor`>`que" () es genérico. El operador mayor que tiene la firma `'a -> 'a -> bool`. No todos los operadores son genéricos y, si el código de una función usa un tipo de parámetro junto con una función o un operador no genéricos, ese tipo de parámetro no se puede generalizar.

Dado `max` que es genérico, se puede usar con tipos `int`como, `float`, etc., como se muestra en los ejemplos siguientes.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Sin embargo, los dos argumentos deben ser del mismo tipo. La firma es `'a -> 'a -> 'a`, no `'a -> 'b -> 'a`. Por lo tanto, el código siguiente genera un error porque los tipos no coinciden.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

La `max` función también funciona con cualquier tipo que admita el operador mayor que. Por lo tanto, también puede utilizarlo en una cadena, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Restricción de valor

El compilador realiza la generalización automática solo en definiciones de función completas que tienen argumentos explícitos y en valores inmutables simples.

Esto significa que el compilador emite un error si se intenta compilar código que no está suficientemente restringido para ser un tipo específico, sino que tampoco se puede generalizar. El mensaje de error para este problema hace referencia a esta restricción en la generalización automática de los valores como *restricción de valor*.

Normalmente, el error de restricción de valor se produce cuando se desea que una construcción sea genérica pero el compilador no tiene información suficiente para generalizarla, o cuando se omite involuntariamente suficiente información de tipo en una construcción no genérica. La solución al error de restricción de valor es proporcionar información más explícita para restringir más el problema de inferencia de tipos de una de las siguientes maneras:

- Restrinja un tipo para que no sea genérico agregando una anotación de tipo explícito a un valor o parámetro.

- Si el problema utiliza una construcción no generalizable para definir una función genérica, como una composición de función o argumentos de función currificados aplicados incompletamente, intente volver a escribir la función como una definición de función normal.

- Si el problema es una expresión que es demasiado compleja para generalizarla, puede convertirla en una función agregando un parámetro adicional sin usar.

- Agregue parámetros de tipo genérico explícitos. Esta opción rara vez se usa.

- En los siguientes ejemplos de código se muestra cada uno de estos escenarios.

Caso 1: Una expresión demasiado compleja. En este ejemplo, la lista `counter` está pensada para `int option ref`ser, pero no se define como un valor inmutable simple.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Caso 2: Usar una construcción no generalizable para definir una función genérica. En este ejemplo, la construcción no es generalizable porque implica la aplicación parcial de argumentos de función.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Caso 3: Agregar un parámetro adicional sin usar. Dado que esta expresión no es lo suficientemente sencilla para la generalización, el compilador emite el error de restricción de valor.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Caso 4: Agregar parámetros de tipo.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

En el último caso, el valor se convierte en una función de tipo, que se puede usar para crear valores de muchos tipos diferentes, como se indica a continuación:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Vea también

- [Inferencia de tipos](../type-inference.md)
- [Genéricos](index.md)
- [Parámetros de tipo resueltos estáticamente](statically-resolved-type-parameters.md)
- [Restricciones](constraints.md)
