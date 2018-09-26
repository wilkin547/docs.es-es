---
title: Parámetros de tipo resueltos estáticamente (F#)
description: 'Obtenga información sobre cómo usar F # parámetro de tipo resueltos estáticamente, que se reemplaza con un tipo real en tiempo de compilación en lugar de en tiempo de ejecución.'
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208268"
---
# <a name="statically-resolved-type-parameters"></a>Parámetros de tipo resueltos estáticamente

Un *parámetro de tipo resueltos estáticamente* es un parámetro de tipo que se reemplaza con un tipo real en tiempo de compilación en lugar de en tiempo de ejecución. Va precedido por el símbolo de intercalación (^).

## <a name="syntax"></a>Sintaxis

```
ˆtype-parameter
```

## <a name="remarks"></a>Comentarios

En el lenguaje F#, hay dos clases de parámetros de tipo. En primer lugar está el parámetro de tipo genérico estándar. Estos parámetros se indican mediante un apóstrofo ('), como en `'T` y `'U`. Equivalen a los parámetros de tipo genérico de otros lenguajes .NET Framework. El otro tipo de parámetro se resuelve estáticamente y se indica mediante el símbolo de intercalación, como en `^T` y `^U`.

Los parámetros de tipo resueltos estáticamente son sobre todo útiles cuando se usan con restricciones de miembro, que son restricciones que permiten especificar que un argumento de tipo debe tener uno o varios miembros determinados. Este tipo de restricción no se puede crear mediante un parámetro de tipo genérico normal.

En la siguiente tabla, se resumen las similitudes y las diferencias entre las dos clases de parámetros de tipo.

|Característica|Genérico|Se resuelve estáticamente|
|-------|-------|-------------------|
|Sintaxis|`'T`, `'U`|`^T`, `^U`|
|Tiempo de resolución|Tiempo de ejecución|Tiempo de compilación|
|Restricciones de miembro|No se puede utilizar con restricciones de miembro.|Se puede utilizar con restricciones de miembro.|
|Generación de código|Un tipo o método con parámetros de tipo genérico estándar da lugar a la generación de un solo tipo o método genérico.|Se generan varias instancias de los tipos y métodos, una por cada tipo que se necesita.|
|Uso con tipos|Se puede utilizar con tipos.|No se puede utilizar con tipos.|
|Uso con funciones inline|No. Una función inline no puede tener un parámetro de tipo genérico estándar.|Sí. Los parámetros de tipo resueltos estáticamente no se pueden utilizar con funciones o métodos que no sean inline.|

Muchas funciones de la biblioteca básica de F#, sobre todo los operadores, tienen parámetros de tipo que se resuelven estáticamente. Se trata de funciones y operadores inline, que dan lugar a una generación de código eficaz para los cálculos numéricos.

Los métodos y funciones inline que usan operadores u otras funciones que utilicen parámetros de tipo resueltos estáticamente, también pueden emplear ellos mismos este tipo de parámetro. En muchas ocasiones, durante la inferencia de tipos, se deduce que esas funciones inline tienen parámetros de tipo que se resuelven estáticamente. En el siguiente ejemplo, se muestra una definición de operador para la cual se deduce que tiene un parámetro de tipo que se resuelve estáticamente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

El tipo resuelto de `(+@)` se basa en el uso de `(+)` y `(*)`, que hacen que mediante la inferencia de tipos se deduzcan las restricciones de miembro en los parámetros de tipo estáticamente resueltos. Tal y como se muestra en el intérprete de F#, el tipo resuelto es el siguiente.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

La salida es la siguiente.

```
2
1.500000
```

A partir de F # 4.1, también puede especificar los nombres de tipo concreto en las firmas de parámetro de tipo resueltos estáticamente.  En versiones anteriores del lenguaje, el nombre de tipo se pudo inferir realmente por el compilador, pero no se puede especificar realmente en la firma.  A partir de F # 4.1, también puede especificar los nombres de tipo concreto en las firmas de parámetro de tipo resueltos estáticamente. Por ejemplo:

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>Vea también

- [Genéricos](index.md)
- [Inferencia de tipos](../type-inference.md)
- [Generalización automática](automatic-generalization.md)
- [Restricciones](constraints.md)
- [Funciones insertadas](../functions/inline-functions.md)
