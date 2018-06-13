---
title: Extensiones de tipo (F#)
description: 'Obtenga información acerca de cómo las extensiones de tipo de F # permiten que agregar a nuevos miembros a un tipo de objeto previamente definido.'
ms.date: 05/16/2016
ms.openlocfilehash: 2181745ea75894fbfe35d5522c130baaf1876455
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566891"
---
# <a name="type-extensions"></a>Extensiones de tipo

Extensiones de tipo permiten agregar a nuevos miembros a un tipo de objeto previamente definido.

## <a name="syntax"></a>Sintaxis

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a>Comentarios
Hay dos formas de extensiones de tipos que tienen comportamientos y una sintaxis ligeramente diferente. Un *extensión intrínseca* es una extensión que aparece en el mismo espacio de nombres o módulo, en el mismo archivo de origen y en el mismo ensamblado (DLL o archivo ejecutable) como el tipo que se va a extender. Un *extensión opcional* es una extensión que aparece fuera del espacio de nombres, módulo o ensamblado del tipo que se extiende original. Las extensiones intrínsecas aparecen en el tipo cuando el tipo se examina mediante reflexión, pero no así las extensiones opcionales. Las extensiones opcionales deben estar en módulos y solo están en ámbito cuando se abre el módulo que contiene la extensión.

En la sintaxis anterior, *typename* representa el tipo que se va a extender. Se puede extender cualquier tipo que se puede tener acceso, pero el nombre de tipo debe ser un nombre de tipo real, no una abreviatura de tipo. Puede definir a varios miembros en una extensión de tipo. El *self-identifier* representa la instancia del objeto que se invoca, al igual que en los miembros normales.

El `end` palabra clave es opcional en sintaxis ligera.

Los miembros definidos en las extensiones de tipo pueden usarse al igual que otros miembros de un tipo de clase. Al igual que otros miembros, pueden ser estáticos o miembros de instancia. Estos métodos son también se denomina *métodos de extensión*; se denominan propiedades *propiedades de extensión*, y así sucesivamente. Miembros de extensión opcional se compilan en miembros estáticos para los que la instancia de objeto se pasa implícitamente como el primer parámetro. Sin embargo, actúan como si fueran miembros de instancia o los miembros estáticos según cómo se declaran. Miembros de extensión implícitos se incluyen como miembros del tipo y pueden utilizarse sin restricciones.

Métodos de extensión no pueden ser métodos virtuales o abstractos. Pueden sobrecargar otros métodos del mismo nombre, pero el compilador da preferencia a los métodos de extensión no en el caso de una llamada ambigua.

Si varias extensiones de tipo intrínseco existen para un tipo, todos los miembros deben ser únicos. Las extensiones de tipo opcional, los miembros de las extensiones de tipo diferente en el mismo tipo pueden tener los mismos nombres. Se producen errores de ambigüedad sólo si el código de cliente abre dos ámbitos diferentes que definen los mismos nombres de miembro.

En el ejemplo siguiente, un tipo de un módulo tiene una extensión de tipo intrínseco. Al código de cliente fuera del módulo, la extensión de tipo aparece como un miembro normal del tipo en todos los sentidos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

Puede utilizar extensiones de tipo intrínsecas para separar la definición de un tipo en secciones. Esto puede ser útil para administrar las definiciones de tipo grande, por ejemplo, para separar el código generado por el compilador y el código creado o agrupar código creados por distintas personas o asociados con una funcionalidad diferente.

En el ejemplo siguiente, una extensión de tipo opcional extiende el `System.Int32` tipo con un método de extensión `FromString` que llama al miembro estático `Parse`. El `testFromString` método muestra que el nuevo miembro se llama igual que cualquier miembro de instancia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

El nuevo miembro de instancia aparecerá como cualquier otro método de la `Int32` tipo en IntelliSense, pero solo cuando el módulo que contiene la extensión está abierto o de otra manera en el ámbito.

## <a name="generic-extension-methods"></a>Métodos de extensión genérico
Antes de F # 3.1, el compilador de F # no admite el uso de C#: aplicar estilo a los métodos de extensión con una variable de tipo genérico, el tipo de matriz, el tipo de tupla o un tipo de función de F # como el parámetro "this". F # 3.1 admite el uso de estos miembros de extensión.

Por ejemplo, en el código de F # 3.1, puede usar los métodos de extensión con firmas similares a la siguiente sintaxis en C#:

```csharp
static member Method<T>(this T input, T other)
```

Este enfoque es especialmente útil cuando el parámetro de tipo genérico está restringido. Además, ahora puede declarar miembros de extensión como el siguiente código de F # y definir un conjunto de métodos de extensión adicional y gran riqueza semántica. En F #, normalmente se definen a los miembros de extensión como se muestra en el ejemplo siguiente:

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

Sin embargo, para un tipo genérico, la variable de tipo puede no ser limitada. Ahora puede declarar un C#-miembro de extensión de estilo en F # para evitar esta limitación. Cuando se combina este tipo de declaración con la característica en línea de F #, se pueden presentar algoritmos genéricos como miembros de extensión.

Considere la siguiente declaración:

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Mediante el uso de esta declaración, puede escribir código similar al ejemplo siguiente.

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

En este código, el mismo código aritmético genérico se aplica a las listas de dos tipos sin la sobrecarga, al definir a un miembro única extensión.


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Miembros](members/index.md)
