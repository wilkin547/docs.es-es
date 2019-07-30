---
title: Interfaces
description: Obtenga información F# sobre cómo las interfaces especifican conjuntos de miembros relacionados que otras clases implementan.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627651"
---
# <a name="interfaces"></a>Interfaces

Las *interfaces* especifican conjuntos de miembros relacionados que otras clases implementan.

## <a name="syntax"></a>Sintaxis

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Comentarios

Las declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro. En su lugar, todos los miembros son abstractos, como se indica `abstract`en la palabra clave. No se proporciona un cuerpo de método para los métodos abstractos. Sin embargo, puede proporcionar una implementación predeterminada al incluir también una definición independiente del miembro como un método junto con la `default` palabra clave. Hacerlo es equivalente a crear un método virtual en una clase base en otros lenguajes .NET. Este tipo de método virtual se puede invalidar en las clases que implementan la interfaz.

La accesibilidad predeterminada para las interfaces `public`es.

Opcionalmente, puede asignar un nombre a cada parámetro de método F# usando la sintaxis normal:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

En el ejemplo `ISprintable` anterior, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format`.

Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y el uso de tipos de clase. En cualquier caso, el tipo de clase o la expresión de objeto proporciona cuerpos de método para los métodos abstractos de la interfaz. Las implementaciones son específicas de cada tipo que implementa la interfaz. Por lo tanto, los métodos de interfaz en tipos diferentes pueden ser diferentes entre sí.

Las palabras `interface` clave `end`y, que marcan el inicio y el final de la definición, son opcionales cuando se usa la sintaxis ligera. Si no usa estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que se usan. Si define un miembro o usa otra sintaxis de clase, el tipo se interpreta como una clase.

El estilo de codificación de .NET consiste en comenzar todas las interfaces `I`con una letra mayúscula.

## <a name="implementing-interfaces-by-using-class-types"></a>Implementar interfaces mediante tipos de clase

Puede implementar una o más interfaces en un tipo de clase mediante la `interface` palabra clave, el nombre de la interfaz y la `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Las implementaciones de interfaz se heredan, por lo que las clases derivadas no necesitan volver a implementarlas.

## <a name="calling-interface-methods"></a>Llamar a métodos de interfaz

Solo se puede llamar a los métodos de interfaz a través de la interfaz, no a través de ningún objeto del tipo que implementa la interfaz. Por lo tanto, es posible que tenga que convertir al tipo de interfaz mediante `:>` el operador o `upcast` el operador para llamar a estos métodos.

Para llamar al método de interfaz cuando tiene un objeto de tipo `SomeClass`, debe convertir el objeto al tipo de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementar interfaces mediante expresiones de objeto

Las expresiones de objeto proporcionan una manera breve de implementar una interfaz. Son útiles cuando no es necesario crear un tipo con nombre y simplemente se desea un objeto que admita los métodos de interfaz, sin ningún método adicional. En el código siguiente se muestra una expresión de objeto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Herencia de interfaz

Las interfaces pueden heredar de una o varias interfaces base.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de objeto](object-expressions.md)
- [Clases](classes.md)
