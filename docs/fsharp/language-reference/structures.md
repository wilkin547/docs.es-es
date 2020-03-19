---
title: Estructuras
description: Obtenga información sobre la estructura de F, un tipo de objeto compacto a menudo más eficaz que una clase para tipos con una pequeña cantidad de datos y un comportamiento simple.
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401128"
---
# <a name="structures"></a>Estructuras

Una *estructura* es un tipo de objeto compacto que puede ser más eficaz que una clase para los tipos que tienen una pequeña cantidad de datos y un comportamiento simple.

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

## <a name="remarks"></a>Observaciones

Las estructuras son tipos de *valor,* lo que significa que se almacenan directamente en la pila o, cuando se utilizan como campos o elementos de matriz, en línea en el tipo primario. A diferencia de los registros y las clases, las estructuras tienen semántica de paso por valor. Esto significa que son útiles principalmente para pequeños agregados de datos a los que accede y que se copian con frecuencia.

En la sintaxis anterior, se muestran dos formularios. La primera no es la sintaxis ligera; sin embargo, se utiliza frecuentemente porque, cuando se usan las palabras clave `struct` y `end`, se puede omitir el atributo `StructAttribute`, que aparece en el segundo formulario. `StructAttribute` se puede abreviar como `Struct`.

El *type-definition-elements-and-members* de la sintaxis anterior representa las declaraciones y definiciones de miembros. Las estructuras pueden tener constructores y campos mutables e inmutables, y pueden declarar implementaciones de interfaces y miembros. Para obtener más información, consulte [Miembros](./members/index.md).

Las estructuras no pueden participar en la herencia, no pueden contener enlaces `let` ni `do`, y no puede contener de forma recursiva campos de su propio tipo (aunque pueden contener celdas de referencia que hagan referencia a su propio tipo).

Dado que las estructuras no permiten enlaces `let`, debe declarar campos en estructuras mediante el uso de la palabra clave `val`. La palabra clave `val` define un campo y su tipo, pero no permite la inicialización. En su lugar, las declaraciones `val` se inicializan en cero o null. Por este motivo, las estructuras que tienen un constructor implícito (es decir, los parámetros que se proporcionan inmediatamente después del nombre de la estructura en la declaración) requieren que las declaraciones `val` se anoten con el atributo `DefaultValue`. Las estructuras que tienen un constructor definido todavía admiten la inicialización en cero. Por lo tanto, el atributo `DefaultValue` es una declaración de que ese valor cero es válido para el campo. Los constructores implícitos de las estructuras no realizan ninguna acción porque los enlaces `let` y `do` no están permitidos en el tipo, pero los valores de parámetro de constructor implícito pasados están disponibles como campos privados.

Los constructores explícitos podrían implicar la inicialización de los valores de campo. Cuando se tiene una estructura con un constructor explícito, se admite la inicialización en cero; sin embargo, no se utiliza el atributo `DefaultValue` en las declaraciones `val` porque entra en conflicto con el constructor explícito. Para obtener `val` más información acerca de las declaraciones, vea [Campos explícitos: `val` la palabra clave](./members/explicit-fields-the-val-keyword.md).

Los atributos y modificadores de accesibilidad están permitidos en las estructuras y siguen las mismas reglas que las de otros tipos. Para obtener más información, consulte [Atributos](attributes.md) y control de [acceso](access-control.md).

Los siguientes ejemplos de código ilustran las definiciones de la estructura.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>Estructuras ByRefLike

Puede definir sus propias estructuras `byref`que se pueden adherir a la semántica -como: consulte [Byrefs](byrefs.md) para obtener más información. Esto se hace <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> con el atributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`no implica `Struct`. Ambos deben estar presentes en el tipo.

Una`byref`estructura " -like" en F es un tipo de valor enlazado a la pila. Nunca se asigna en el montón administrado. Una `byref`estructura -like es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones sólidas sobre la duración y la no captura. Las reglas son:

- Se pueden utilizar como parámetros de función, parámetros de método, variables locales, retornos de método.
- No pueden ser miembros estáticos o de instancia de una clase o estructura normal.
- No se pueden capturar mediante`async` ninguna construcción de cierre (métodos o expresiones lambda).
- No se pueden utilizar como parámetro genérico.

Aunque estas reglas restringen fuertemente el uso, lo hacen para cumplir la promesa de la informática de alto rendimiento de una manera segura.

## <a name="readonly-structs"></a>Estructuras ReadOnly

Puede anotar estructuras <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> con el atributo. Por ejemplo:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly`no implica `Struct`. Debe agregar ambos para `IsReadOnly` tener una estructura.

El uso de este atributo emite metadatos que permiten `inref<'T>` que `in ref`F- y C- sepan tratarlo como y , respectivamente.

Definir un valor mutable dentro de una estructura readonly produce un error.

## <a name="struct-records-and-discriminated-unions"></a>Struct Records y Uniones Discriminadas

Puede representar [Registros](records.md) y [Uniones discriminadas](discriminated-unions.md) como estructuras con el `[<Struct>]` atributo.  Consulte cada artículo para obtener más información.

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje f](index.md)
- [Clases](classes.md)
- [Registros](records.md)
- [Miembros](./members/index.md)
