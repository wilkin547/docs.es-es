---
title: Enumeraciones (F#)
description: 'Obtenga información acerca de cómo usar las enumeraciones de F # en lugar de literales para que el código más legible y fácil de mantener.'
ms.date: 05/16/2016
ms.openlocfilehash: 00faf6e2ad08a7b232a8ae35aa0f7deb1ba3e76a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="enumerations"></a>Enumeraciones

*Enumeraciones*, también conocida como *enumeraciones*, son tipos integrales donde las etiquetas están asignadas a un subconjunto de los valores. Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.


## <a name="syntax"></a>Sintaxis

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Comentarios
Una enumeración se parece mucho a una unión discriminada con valores simples, salvo que se pueden especificar los valores. Los valores son normalmente enteros que representan las posiciones de bits o enteros que empiezan en 0 o 1. Si una enumeración está pensada para representar posiciones de bits, también debe usar el [marcas](xref:System.FlagsAttribute) atributo.

El tipo subyacente de la enumeración se determina a partir del valor literal que se usa, por lo que, por ejemplo, puede usar literales con sufijo, como `1u`, `2u`, y así sucesivamente, para un entero sin signo (`uint32`) tipo.

Cuando se hace referencia a los valores con nombre, debe utilizar el nombre del propio tipo de enumeración como calificador, es decir, `enum-name.value1`, no sólo `value1`. Este comportamiento difiere del de las uniones discriminadas. Esto es porque las enumeraciones siempre tienen la [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo.

El código siguiente muestra la declaración y el uso de una enumeración.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Fácilmente puede convertir enumeraciones en el tipo subyacente mediante el operador adecuado, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Los tipos enumerados pueden tener uno de los tipos subyacentes siguientes: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, y `char`. Tipos de enumeración se representan en .NET Framework como tipos que se heredan de `System.Enum`, que a su vez se hereda de `System.ValueType`. Por lo tanto, son tipos de valores que se encuentran en la pila o en línea en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración. Esto es importante cuando los valores de coincidencia de patrones en la enumeración, ya que tendrá que proporcionar un patrón que detecta los valores sin nombre.

El `enum` función en la biblioteca de F # puede utilizarse para generar un valor de enumeración, incluso un valor distinto de predefinido, valores con nombre. Usa el `enum` funcione como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

El valor predeterminado `enum` función funciona con el tipo de `int32`. Por lo tanto, no puede usarse con tipos de enumeración que tienen otros tipos subyacentes. En su lugar, utilice el siguiente código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Conversiones](casting-and-conversions.md)
