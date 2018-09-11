---
title: Estructuras (F#)
description: 'Obtenga información sobre la estructura de F #, un tipo de objeto compacto a menudo más eficaz que una clase para los tipos con una pequeña cantidad de datos y un comportamiento simple.'
ms.date: 05/16/2016
ms.openlocfilehash: 08af88132dda28883e246b94585ff4ed8bd2f16a
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337960"
---
# <a name="structures"></a>Estructuras

Un *estructura* es un tipo de objeto compacto que puede ser más eficaz que una clase para tipos que tienen una pequeña cantidad de datos y un comportamiento simple.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a>Comentarios

Las estructuras son *los tipos de valor*, lo que significa que se almacenan directamente en la pila o, cuando se usan como campos o los elementos de matriz, alineados en el elemento primario del tipo. A diferencia de los registros y las clases, las estructuras tienen semántica de paso por valor. Esto significa que son útiles principalmente para pequeños agregados de datos a los que accede y que se copian con frecuencia.

En la sintaxis anterior, se muestran dos formularios. La primera no es la sintaxis ligera; sin embargo, se utiliza frecuentemente porque, cuando se usan las palabras clave `struct` y `end`, se puede omitir el atributo `StructAttribute`, que aparece en el segundo formulario. `StructAttribute` se puede abreviar como `Struct`.

El *-definition-elementos-y-miembros de tipo* en la sintaxis anterior representa definiciones y declaraciones de miembros. Las estructuras pueden tener constructores y campos mutables e inmutables, y pueden declarar implementaciones de interfaces y miembros. Para obtener más información, consulte [miembros](members/index.md).

Las estructuras no pueden participar en la herencia, no pueden contener enlaces `let` ni `do`, y no puede contener de forma recursiva campos de su propio tipo (aunque pueden contener celdas de referencia que hagan referencia a su propio tipo).

Dado que las estructuras no permiten enlaces `let`, debe declarar campos en estructuras mediante el uso de la palabra clave `val`. La palabra clave `val` define un campo y su tipo, pero no permite la inicialización. En su lugar, las declaraciones `val` se inicializan en cero o null. Por este motivo, las estructuras que tienen un constructor implícito (es decir, los parámetros que se proporcionan inmediatamente después del nombre de la estructura en la declaración) requieren que las declaraciones `val` se anoten con el atributo `DefaultValue`. Las estructuras que tienen un constructor definido todavía admiten la inicialización en cero. Por lo tanto, el atributo `DefaultValue` es una declaración de que ese valor cero es válido para el campo. Los constructores implícitos de las estructuras no realizan ninguna acción porque los enlaces `let` y `do` no están permitidos en el tipo, pero los valores de parámetro de constructor implícito pasados están disponibles como campos privados.

Los constructores explícitos podrían implicar la inicialización de los valores de campo. Cuando se tiene una estructura con un constructor explícito, se admite la inicialización en cero; sin embargo, no se utiliza el atributo `DefaultValue` en las declaraciones `val` porque entra en conflicto con el constructor explícito. Para obtener más información acerca de `val` declaraciones, vea [campos explícitos: el `val` palabra clave](members/explicit-fields-the-val-keyword.md).

Los atributos y modificadores de accesibilidad están permitidos en las estructuras y siguen las mismas reglas que las de otros tipos. Para obtener más información, consulte [atributos](attributes.md) y [Control de acceso](access-control.md).

Los siguientes ejemplos de código ilustran las definiciones de la estructura.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>Structs ByRefLike

Puede definir sus propias estructuras que pueden cumplir `byref`-como semántica: vea [Zkratka](byrefs.md) para obtener más información. Esto se realiza con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` no implica `Struct`. Deben estar presentes en el tipo.

Un "`byref`-como" struct en F # es un tipo de valor de límite de la pila. Nunca se asigna en el montón administrado. Un `byref`-como struct es útil para la programación de alto rendimiento, ya que se aplica con el conjunto de controles sólidos sobre la duración y no captura. Las reglas son:

* Se puede usar como parámetros de función, parámetros de método, las variables locales, devuelve el método.
* Que no pueden ser estáticos o miembros de una clase o estructura normal de instancia.
* No se puede capturar cualquier construcción de cierre (`async` métodos o expresiones lambda).
* No se puede usar como un parámetro genérico.

Aunque estas reglas encarecidamente restringen el uso, lo hacen para cumplir la promesa de informática de alto rendimiento de una manera segura.

## <a name="readonly-structs"></a>Estructuras ReadOnly

Puede anotar structs con el <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> atributo. Por ejemplo:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly` no implica `Struct`. Debe agregar ambos para tener un `IsReadOnly` struct.

Uso de este atributo emite metadatos, lo que permite F # y C# saber para tratarlo como `inref<'T>` y `in ref`, respectivamente.

Definir un valor mutable dentro de un struct de solo lectura, produce un error.

## <a name="struct-records-and-discriminated-unions"></a>Struct registros y uniones discriminadas

Puede representar [registros](records.md) y [uniones discriminadas](discriminated-unions.md) como structs con el `[<Struct>]` atributo.  Vea cada artículo para obtener más información.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Clases](classes.md)
- [Registros](records.md)
- [Miembros](members/index.md)
