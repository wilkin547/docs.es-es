---
title: Extensiones de tipo (F#)
description: 'Obtenga información sobre cómo las extensiones de tipo de F # permiten que agregar a nuevos miembros a un tipo de objeto previamente definido.'
ms.date: 07/20/2018
ms.openlocfilehash: 2181745ea75894fbfe35d5522c130baaf1876455
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "33566891"
---
# <a name="type-extensions"></a>Extensiones de tipo

Extensiones de tipo (también denominada _aumentos_) es una familia de características que permiten agregar nuevos miembros a un tipo de objeto previamente definido. Las tres características son:

* Extensiones de tipo intrínseco
* Extensiones de tipo opcional
* Métodos de extensión

Cada una puede usarse en escenarios diferentes y ofrece un equilibrio entre diferentes.

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

## <a name="intrinsic-type-extensions"></a>Extensiones de tipo intrínseco

Una extensión de tipo intrínseco es un tipo que extiende un tipo definido por el usuario.

Extensiones de tipo intrínsecas deben definirse en el mismo archivo **y** en el mismo espacio de nombres o módulo como el tipo que están extendiendo. Cualquier otra definición hará que se va a [las extensiones de tipo opcional](type-extensions.md#optional-type-extensions).

Las extensiones de tipo intrínseco a veces son una forma más limpia para separar la funcionalidad de la declaración de tipos. El ejemplo siguiente muestra cómo definir una extensión de tipo intrínseco:

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

Uso de una extensión de tipo le permite separar cada una de las siguientes acciones:

* La declaración de un `Variant` tipo
* Funcionalidad para imprimir el `Variant` clase dependiendo de su forma de""
* Una manera de obtener acceso a la funcionalidad de impresión con estilo de objeto `.`-notación

Esta es una alternativa a la definición de todo el contenido como un miembro en `Variant`. Aunque no es un enfoque mejor de manera inherente, puede ser una representación más limpia de funcionalidad en algunas situaciones.

Extensiones de tipo intrínsecas se compilan como miembros del tipo aumentar y que aparecen en el tipo cuando el tipo se examina mediante reflexión.

## <a name="optional-type-extensions"></a>Extensiones de tipo opcional

Una extensión de tipo opcional es una extensión que aparece fuera del espacio de nombres, módulo o ensamblado del tipo que se extiende original.

Las extensiones de tipo opcionales son útiles para extender un tipo que no haya definido usted mismo. Por ejemplo:

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

Ahora puede acceder a `RepeatElements` como si fuera un miembro de <xref:System.Collections.Generic.IEnumerable%601> siempre y cuando el `Extensions` módulo se abre en el ámbito que está trabajando en.

Las extensiones opcionales no aparecen en el tipo extendido cuando se examina mediante reflexión. Las extensiones opcionales deben estar en módulos y están solo en el ámbito cuando el módulo que contiene la extensión está abierto o si no está en el ámbito.

Miembros de extensión opcionales se compilan en miembros estáticos para el que la instancia del objeto se pasa implícitamente como primer parámetro. Sin embargo, actúan como si fueran miembros de instancia o miembros estáticos según cómo se declaran.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>Limitación genérico de las extensiones de tipo intrínseco y opcionales

Es posible declarar una extensión de tipo en un tipo genérico que se restringe la variable de tipo. El requisito es que la restricción de la declaración de la extensión coincide con la restricción del tipo declarado.

Sin embargo, incluso cuando se cumplen las restricciones entre un tipo declarado y una extensión de tipo, es posible que se puede inferir el cuerpo de un miembro extendido que impone un requisito distinto en el parámetro de tipo que el tipo declarado para una restricción. Por ejemplo:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

No hay ninguna manera de obtener este código funcione con una extensión de tipo opcional:

* Tal como está, el `Sum` miembro tiene una restricción diferentes en `'T` (`static member get_Zero` y `static member (+)`) que lo que define la extensión del tipo.
* Modificación de la extensión de tipo para que tenga la misma restricción como `Sum` dejarán de coincidir con la restricción definida en `IEnumerable<'T>`.
* Hacer que cambiar el miembro `member inline Sum` generará un error que no coinciden las restricciones de tipo

¿Qué es el deseado son métodos estáticos que "flotar en el espacio" y se pueden presentar como si va a extender un tipo. Esto es donde los métodos de extensión que sea necesarios.

## <a name="extension-methods"></a>Métodos de extensión

Por último, los métodos de extensión (a veces denominados a "miembros extensión de estilo C#") pueden declararse en F # como un método de miembro estático en una clase.

Métodos de extensión son útiles para cuando desee definir extensiones en un tipo genérico que restringirá la variable de tipo. Por ejemplo:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Cuando se utiliza, este código lo que aparezca como si `Sum` se define en <xref:System.Collections.Generic.IEnumerable%601>, siempre y cuando `Extensions` se ha abierto o está en el ámbito.

## <a name="other-remarks"></a>Otros comentarios

Las extensiones de tipo también tienen los siguientes atributos:

* Se puede extender cualquier tipo que se puede tener acceso.
* Pueden definir extensiones de tipo intrínsecas y opcional _cualquier_ tipo de miembro, no solo métodos. Por lo que las propiedades de extensión también son posibles, por ejemplo.
* El `self-identifier` token en el [sintaxis](type-extensions.md#syntax) representa la instancia del tipo que se invoca, igual que los miembros normales.
* Miembros extendidos pueden ser estáticos o miembros de instancia.
* Las variables de tipo en una extensión de tipo deben coincidir con las restricciones del tipo declarado.

También existen las siguientes limitaciones para las extensiones de tipo:

* Las extensiones de tipo no admiten métodos virtuales o abstractos.
* Las extensiones de tipo no admiten los métodos de invalidación como aumentos.
* No se admiten las extensiones de tipo [parámetros tipo resueltos estáticamente](generics/statically-resolved-type-parameters.md).
* Extensiones de tipo opcionales no admiten constructores como aumentos.
* Las extensiones de tipo no se pueden definir en [abreviaturas de tipo](type-abbreviations.md).
* Las extensiones de tipo no son válidas para `byref<'T>` (aunque se puede declarar).
* Las extensiones de tipo no son válidas para los atributos (aunque se puede declarar).
* Puede definir extensiones que sobrecargan otros métodos del mismo nombre, pero el compilador de F # da preferencia a los métodos que no sean de extensión si hay una llamada ambigua.

Por último, si existen varias extensiones de tipo intrínsecas para un tipo, todos los miembros deben ser únicos. Para las extensiones de tipo opcional, los miembros de las extensiones de tipo diferente en el mismo tipo pueden tener los mismos nombres. Se producen errores de ambigüedad sólo si el código de cliente abre dos ámbitos diferentes que definen los mismos nombres de miembro.

## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)

[Miembros](members/index.md)
