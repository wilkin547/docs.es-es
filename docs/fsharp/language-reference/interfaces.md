---
title: Interfaces (F#)
description: 'Obtenga información acerca de cómo F # Interfaces especificar conjuntos de miembros relacionados que otras clases implementan.'
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058906"
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
Declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro. En su lugar, todos los miembros son abstractos, tal como se indica mediante la palabra clave `abstract`. No se proporciona un cuerpo de método para los métodos abstractos. Sin embargo, puede proporcionar una implementación predeterminada también incluye una definición independiente del miembro como método junto con el `default` palabra clave. Esto es equivalente a la creación de un método virtual en una clase base en otros lenguajes. NET. Este tipo de método virtual puede reemplazarse en las clases que implementan la interfaz.

La accesibilidad predeterminada para las interfaces es `public`.

También puede asignar a cada parámetro de método un nombre que se usa la sintaxis normal de F #:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

En los pasos anteriores `ISprintable` ejemplo, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format`.

Hay dos maneras de implementar interfaces: mediante expresiones de objeto y mediante el uso de tipos de clase. En cualquier caso, la expresión de tipo u objeto de clase proporciona cuerpos de método para los métodos abstractos de la interfaz. Las implementaciones son específicas para cada tipo que implementa la interfaz. Por lo tanto, los métodos de interfaz en diferentes tipos puede variar entre sí.

Las palabras clave `interface` y `end`, que marca el inicio y el final de la definición, son opcionales cuando emplee la sintaxis ligera. Si no utiliza estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz analizando las construcciones que usan. Si se define un miembro o utilizar otra sintaxis de clase, el tipo se interpreta como una clase.

El estilo de codificación de .NET consiste en empezar a todas las interfaces con una letra mayúscula `I`.


## <a name="implementing-interfaces-by-using-class-types"></a>Implementar Interfaces mediante tipos de clase
Puede implementar una o varias interfaces en un tipo de clase mediante el `interface` palabra clave, el nombre de la interfaz y la `with` (palabra clave), seguido de las definiciones de miembro de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Implementaciones de interfaz se heredan, por lo que no es necesario que las clases derivadas implementarlas.


## <a name="calling-interface-methods"></a>Llamar a métodos de interfaz
Pueden llamar a métodos de interfaz sólo a través de la interfaz, no a través de cualquier objeto del tipo que implementa la interfaz. Por lo tanto, es posible que deba conversión hacia arriba para el tipo de interfaz mediante el uso de la `:>` operador o la `upcast` operador para poder llamar a estos métodos.

Para llamar al método de interfaz cuando se tiene un objeto de tipo `SomeClass`, debe conversión hacia arriba el objeto al tipo de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Una alternativa consiste en declarar un método en el objeto que convierte y llama al método de interfaz, como en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementar Interfaces mediante expresiones de objeto
Expresiones de objeto proporcionan una manera abreviada para implementar una interfaz. Son útiles cuando no tienes que volver a crear un tipo con nombre y su intención es un objeto que es compatible con los métodos de interfaz, sin ningún método adicional. Una expresión de objeto se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>Herencia de interfaz
Interfaces pueden heredar de una o más interfaces base.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Expresiones de objeto](object-expressions.md)

[Clases](classes.md)
