---
title: Interfaces
description: 'Obtenga información sobre cómo las interfaces de F # especifican conjuntos de miembros relacionados que otras clases implementan.'
ms.date: 08/15/2020
ms.openlocfilehash: 36272b52fcff83e8e8a54ccc4e6ecd1252a91819
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558132"
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

Las declaraciones de interfaz son similares a las declaraciones de clase, salvo que no se implementa ningún miembro. En su lugar, todos los miembros son abstractos, como se indica en la palabra clave `abstract` . No se proporciona un cuerpo de método para los métodos abstractos. Sin embargo, puede proporcionar una implementación predeterminada al incluir también una definición independiente del miembro como un método junto con la `default` palabra clave. Hacerlo es equivalente a crear un método virtual en una clase base en otros lenguajes .NET. Este tipo de método virtual se puede invalidar en las clases que implementan la interfaz.

La accesibilidad predeterminada para las interfaces es `public` .

Opcionalmente, puede asignar un nombre a cada parámetro de método mediante la sintaxis de F # normal:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

En el `ISprintable` ejemplo anterior, el `Print` método tiene un único parámetro del tipo `string` con el nombre `format` .

Hay dos maneras de implementar interfaces: mediante el uso de expresiones de objeto y el uso de tipos de clase. En cualquier caso, el tipo de clase o la expresión de objeto proporciona cuerpos de método para los métodos abstractos de la interfaz. Las implementaciones son específicas de cada tipo que implementa la interfaz. Por lo tanto, los métodos de interfaz en tipos diferentes pueden ser diferentes entre sí.

Las palabras clave `interface` y `end` , que marcan el inicio y el final de la definición, son opcionales cuando se usa la sintaxis ligera. Si no usa estas palabras clave, el compilador intenta deducir si el tipo es una clase o una interfaz mediante el análisis de las construcciones que se usan. Si define un miembro o usa otra sintaxis de clase, el tipo se interpreta como una clase.

El estilo de codificación de .NET consiste en comenzar todas las interfaces con una letra mayúscula `I` .

Puede especificar varios parámetros de dos maneras: F #-Style y. Estilo de red. Ambos se compilarán de la misma manera para los consumidores de .NET, pero F #-Style forzará a los autores de llamadas de F # a usar la aplicación de parámetros de estilo F # y. El estilo de red obliga a los autores de llamadas de F # a usar la aplicación de argumentos de tupla.

```fsharp
type INumeric1 =
    abstract Add: x: int -> y: int -> int

type INumeric2 =
    abstract Add: x: int * y: int -> int
```

## <a name="implementing-interfaces-by-using-class-types"></a>Implementar interfaces mediante tipos de clase

Puede implementar una o más interfaces en un tipo de clase mediante la `interface` palabra clave, el nombre de la interfaz y la `with` palabra clave, seguida de las definiciones de miembro de interfaz, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Las implementaciones de interfaz se heredan, por lo que las clases derivadas no necesitan volver a implementarlas.

## <a name="calling-interface-methods"></a>Llamar a métodos de interfaz

Solo se puede llamar a los métodos de interfaz a través de la interfaz, no a través de ningún objeto del tipo que implementa la interfaz. Por lo tanto, es posible que tenga que convertir al tipo de interfaz mediante el `:>` operador o el `upcast` operador para llamar a estos métodos.

Para llamar al método de interfaz cuando tiene un objeto de tipo `SomeClass` , debe convertir el objeto al tipo de interfaz, como se muestra en el código siguiente.

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
