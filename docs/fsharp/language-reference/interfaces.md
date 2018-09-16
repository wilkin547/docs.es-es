---
title: Interfaces (F#)
description: 'Obtenga información sobre cómo las Interfaces de F # especificar conjuntos de miembros relacionados que otras clases implementan.'
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45683195"
---
# <a name="interfaces"></a>Interfaces

*Interfaces* especificar conjuntos de miembros relacionados que otras clases implementan.

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

Declaraciones de interfaz son similares a las declaraciones de clase, salvo que no implementan miembros. En su lugar, todos los miembros son abstractos, tal como se indica mediante la palabra clave `abstract`. No se proporcionan un cuerpo de método para los métodos abstractos. Sin embargo, puede proporcionar una implementación predeterminada también incluyendo una definición independiente del miembro como un método junto con el `default` palabra clave. Si lo hace, es equivalente a la creación de un método virtual en una clase base en otros lenguajes. NET. Este tipo de método virtual se puede invalidar en clases que implementan la interfaz.

La accesibilidad predeterminada para las interfaces es `public`.

Se puede asignar a cada parámetro del método un nombre utilizando la sintaxis normal de F #:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

En la fórmula anterior `ISprintable` ejemplo, el `Print` método tiene un parámetro único del tipo `string` con el nombre `format`.

Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y mediante el uso de tipos de clase. En cualquier caso, la expresión de tipo u objeto de clase proporciona los cuerpos de método para los métodos abstractos de la interfaz. Las implementaciones son específicas de cada tipo que implementa la interfaz. Por lo tanto, los métodos de interfaz en diferentes tipos pueden variar entre sí.

Las palabras clave `interface` y `end`, que marca el inicio y finalización de la definición, son opcionales cuando se usa la sintaxis ligera. Si no utiliza estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que usan. Si se define un miembro o usar otras sintaxis de la clase, el tipo se interpreta como una clase.

El estilo de codificación de .NET consiste en empezar a todas las interfaces con una letra mayúscula `I`.

## <a name="implementing-interfaces-by-using-class-types"></a>Implementar Interfaces mediante tipos de clase

Puede implementar una o varias interfaces en un tipo de clase mediante el `interface` palabra clave, el nombre de la interfaz y el `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Implementaciones de interfaz se heredan, por lo que cualquier clase derivada no es necesario volver a implementar en ellos.

## <a name="calling-interface-methods"></a>Llamar a métodos de interfaz

Los métodos de interfaz se pueden llamar solo a través de la interfaz, no a través de cualquier objeto del tipo que implementa la interfaz. Por lo tanto, es posible que deba conversión hacia arriba en el tipo de interfaz mediante el uso de la `:>` operador o la `upcast` operador para poder llamar a estos métodos.

Para llamar al método de interfaz cuando tenga un objeto de tipo `SomeClass`, debe upcast el objeto al tipo de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementar Interfaces mediante expresiones de objeto

Expresiones de objeto proporcionan una forma rápida para implementar una interfaz. Son útiles cuando no es necesario que crear un tipo con nombre, y tan solo quiere un objeto que admite los métodos de interfaz sin métodos adicionales. Una expresión de objeto se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Herencia de interfaz

Interfaces pueden heredar de una o varias interfaces bases.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de objeto](object-expressions.md)
- [Clases](classes.md)
