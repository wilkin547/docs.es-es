---
title: Estructuras (F#)
description: "Obtenga información acerca de la estructura de F #, un tipo de objeto compact a menudo más eficaz que una clase para los tipos con una pequeña cantidad de datos y un comportamiento simple."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a>Estructuras

A *estructura* es un tipo de objeto compacto que puede ser más eficaz que una clase para tipos que tienen una pequeña cantidad de datos y un comportamiento simple.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a>Comentarios
Las estructuras son *los tipos de valor*, lo que significa que se almacenan directamente en la pila o, cuando se usan como campos o elementos de matriz, en línea en el elemento primario del tipo. A diferencia de los registros y las clases, las estructuras tienen semántica de paso por valor. Esto significa que son útiles principalmente para pequeños agregados de datos a los que accede y que se copian con frecuencia.

En la sintaxis anterior, se muestran dos formularios. La primera no es la sintaxis ligera; sin embargo, se utiliza frecuentemente porque, cuando se usan las palabras clave `struct` y `end`, se puede omitir el atributo `StructAttribute`, que aparece en el segundo formulario. `StructAttribute` se puede abreviar como `Struct`.

El *elementos de definición de tipo* en la sintaxis anterior representa definiciones y declaraciones de miembros. Las estructuras pueden tener constructores y campos mutables e inmutables, y pueden declarar implementaciones de interfaces y miembros. Para obtener más información, consulte [miembros](members/index.md).

Las estructuras no pueden participar en la herencia, no pueden contener enlaces `let` ni `do`, y no puede contener de forma recursiva campos de su propio tipo (aunque pueden contener celdas de referencia que hagan referencia a su propio tipo).

Dado que las estructuras no permiten enlaces `let`, debe declarar campos en estructuras mediante el uso de la palabra clave `val`. La palabra clave `val` define un campo y su tipo, pero no permite la inicialización. En su lugar, las declaraciones `val` se inicializan en cero o null. Por este motivo, las estructuras que tienen un constructor implícito (es decir, los parámetros que se proporcionan inmediatamente después del nombre de la estructura en la declaración) requieren que las declaraciones `val` se anoten con el atributo `DefaultValue`. Las estructuras que tienen un constructor definido todavía admiten la inicialización en cero. Por lo tanto, el atributo `DefaultValue` es una declaración de que ese valor cero es válido para el campo. Los constructores implícitos de las estructuras no realizan ninguna acción porque los enlaces `let` y `do` no están permitidos en el tipo, pero los valores de parámetro de constructor implícito pasados están disponibles como campos privados.

Los constructores explícitos podrían implicar la inicialización de los valores de campo. Cuando se tiene una estructura con un constructor explícito, se admite la inicialización en cero; sin embargo, no se utiliza el atributo `DefaultValue` en las declaraciones `val` porque entra en conflicto con el constructor explícito. Para obtener más información acerca de `val` declaraciones, vea [campos explícitos: el `val` palabra clave](members/explicit-fields-the-val-keyword.md).

Los atributos y modificadores de accesibilidad están permitidos en las estructuras y siguen las mismas reglas que las de otros tipos. Para obtener más información, consulte [atributos](attributes.md) y [el Control de acceso](access-control.md).

Los siguientes ejemplos de código ilustran las definiciones de la estructura.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a>Struct registros y uniones discriminadas

A partir de F # 4.1, puede representar [registros](records.md) y [uniones discriminadas](discriminated-unions.md) como estructuras con el `[<Struct>]` atributo.  Vea cada artículo para obtener más información.
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Clases](classes.md)

[Registros](records.md)

[Miembros](members/index.md)
