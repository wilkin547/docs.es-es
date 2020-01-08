---
title: Extensiones de tipo
description: Obtenga información F# sobre cómo las extensiones de tipo permiten agregar nuevos miembros a un tipo de objeto definido previamente.
ms.date: 11/04/2019
ms.openlocfilehash: 3e2c6971156bd562ed5d5428e6b7ffdc520c4cf5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341567"
---
# <a name="type-extensions"></a>Extensiones de tipo

Las extensiones de tipo (también denominadas _aumentos_) son una familia de características que permiten agregar nuevos miembros a un tipo de objeto definido previamente. Las tres características son:

- Extensiones de tipo intrínsecas
- Extensiones de tipo opcionales
- Métodos de extensión

Cada se puede usar en escenarios diferentes y tiene diferentes inconvenientes.

## <a name="syntax"></a>Sintaxis

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a>Extensiones de tipo intrínsecas

Una extensión de tipo intrínseco es una extensión de tipo que extiende un tipo definido por el usuario.

Las extensiones de tipo intrínseco se deben definir en el mismo archivo **y** en el mismo espacio de nombres o módulo que el tipo que están extendiendo. Cualquier otra definición dará como resultado extensiones de [tipo opcionales](type-extensions.md#optional-type-extensions).

Las extensiones de tipo intrínseco a veces son una forma más limpia de separar la funcionalidad de la declaración de tipos. En el ejemplo siguiente se muestra cómo definir una extensión de tipo intrínseco:

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

El uso de una extensión de tipo le permite separar cada uno de los elementos siguientes:

- Declaración de un tipo de `Variant`
- Funcionalidad para imprimir la clase `Variant` en función de su "forma"
- Una manera de tener acceso a la funcionalidad de impresión con la notación de `.`de estilo de objeto

Esta es una alternativa a la definición de todo como miembro en `Variant`. Aunque no es un enfoque bastante mejor, puede ser una representación más limpia de la funcionalidad en algunas situaciones.

Las extensiones de tipo intrínseco se compilan como miembros del tipo que aumentan y aparecen en el tipo cuando la reflexión examina el tipo.

## <a name="optional-type-extensions"></a>Extensiones de tipo opcionales

Una extensión de tipo opcional es una extensión que aparece fuera del módulo, espacio de nombres o ensamblado original del tipo que se va a extender.

Las extensiones de tipo opcionales son útiles para extender un tipo que no se ha definido. Por ejemplo:

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

Ahora puede tener acceso a `RepeatElements` como si es miembro de <xref:System.Collections.Generic.IEnumerable%601> siempre que el módulo de `Extensions` se abra en el ámbito en el que está trabajando.

Las extensiones opcionales no aparecen en el tipo extendido cuando se examinan por reflexión. Las extensiones opcionales deben estar en módulos y solo están en el ámbito cuando el módulo que contiene la extensión está abierto o está en el ámbito de otra forma.

Los miembros de extensión opcionales se compilan en miembros estáticos para los que la instancia de objeto se pasa implícitamente como el primer parámetro. Sin embargo, actúan como si fueran miembros de instancia o miembros estáticos según cómo se declaran.

Los miembros de extensión opcionales tampoco son visibles C# para los consumidores o Visual Basic. Solo se pueden consumir en otro F# código.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>Limitación genérica de las extensiones de tipo intrínsecas y opcionales

Es posible declarar una extensión de tipo en un tipo genérico en el que la variable de tipo está restringida. El requisito es que la restricción de la declaración de extensión coincide con la restricción del tipo declarado.

Sin embargo, incluso cuando se hace coincidir las restricciones entre un tipo declarado y una extensión de tipo, es posible que una restricción se infiera por el cuerpo de un miembro extendido que impone un requisito diferente en el parámetro de tipo que el tipo declarado. Por ejemplo:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

No hay ninguna manera de obtener este código para trabajar con una extensión de tipo opcional:

- Tal y como está, el miembro de `Sum` tiene una restricción diferente en `'T` (`static member get_Zero` y `static member (+)`) de la que define la extensión de tipo.
- La modificación de la extensión de tipo para que tenga la misma restricción que `Sum` ya no coincidirá con la restricción definida en `IEnumerable<'T>`.
- Al cambiar `member this.Sum` a `member inline this.Sum`, se producirá un error que indica que las restricciones de tipo no coinciden.

Lo que se desea son los métodos estáticos que "flotan espacio" y se pueden presentar como si estuvieran extendiendo un tipo. Aquí es donde los métodos de extensión son necesarios.

## <a name="extension-methods"></a>Métodos de extensión

Por último, los métodos de extensión (C# a veces denominados "miembros de extensión de F# estilo") se pueden declarar en como un método de miembro estático en una clase.

Los métodos de extensión son útiles cuando se desea definir extensiones en un tipo genérico que restrinja la variable de tipo. Por ejemplo:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Cuando se usa, este código aparecerá como si `Sum` se define en <xref:System.Collections.Generic.IEnumerable%601>, siempre y cuando `Extensions` se haya abierto o esté en el ámbito.

## <a name="other-remarks"></a>Otros comentarios

Las extensiones de tipo también tienen los siguientes atributos:

- Se puede extender cualquier tipo al que se pueda tener acceso.
- Las extensiones de tipo intrínseca y opcional pueden definir _cualquier_ tipo de miembro, no solo los métodos. Por ejemplo, las propiedades de extensión también son posibles.
- El token de `self-identifier` en la [Sintaxis](type-extensions.md#syntax) representa la instancia del tipo que se invoca, al igual que los miembros ordinarios.
- Los miembros extendidos pueden ser miembros estáticos o de instancia.
- Las variables de tipo en una extensión de tipo deben coincidir con las restricciones del tipo declarado.

También existen las siguientes limitaciones para las extensiones de tipo:

- Las extensiones de tipo no admiten métodos virtuales o abstractos.
- Las extensiones de tipo no admiten métodos de invalidación como aumentos.
- Las extensiones de tipo no admiten [parámetros de tipo resueltos estáticamente](./generics/statically-resolved-type-parameters.md).
- Las extensiones de tipo opcionales no admiten constructores como aumentos.
- Las extensiones de tipo no se pueden definir en las [abreviaturas de tipo](type-abbreviations.md).
- Las extensiones de tipo no son válidas para `byref<'T>` (aunque se pueden declarar).
- Las extensiones de tipo no son válidas para los atributos (aunque se pueden declarar).
- Puede definir extensiones que sobrecarguen otros métodos del mismo nombre, pero el F# compilador da preferencia a los métodos que no son de extensión si hay una llamada ambigua.

Por último, si existen varias extensiones de tipo intrínsecas para un tipo, todos los miembros deben ser únicos. En el caso de las extensiones de tipo opcionales, los miembros de diferentes extensiones de tipo al mismo tipo pueden tener los mismos nombres. Los errores de ambigüedad solo se producen si el código de cliente abre dos ámbitos diferentes que definen los mismos nombres de miembro.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Miembros](./members/index.md)
