---
title: Enumeraciones
description: 'Obtenga información sobre cómo usar las enumeraciones de F # en lugar de literales para que el código sea más legible y fácil de mantener.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812112"
---
# <a name="enumerations"></a>Enumeraciones

Las *enumeraciones*, también conocidas como *enumeraciones*,, son tipos enteros donde las etiquetas se asignan a un subconjunto de los valores. Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.

## <a name="syntax"></a>Sintaxis

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Comentarios

Una enumeración es muy similar a una Unión discriminada que tiene valores simples, con la excepción de que se pueden especificar los valores. Los valores suelen ser enteros que comienzan en 0 o 1, o enteros que representan posiciones de bits. Si una enumeración está pensada para representar posiciones de bits, debe usar también el atributo [Flags](xref:System.FlagsAttribute) .

El tipo subyacente de la enumeración se determina a partir del literal que se utiliza, de modo que, por ejemplo, puede usar literales con un sufijo, como `1u` , `2u` , etc., para un tipo entero () sin signo `uint32` .

Cuando se hace referencia a los valores con nombre, debe usar el nombre del tipo de enumeración como calificador, es decir, `enum-name.value1` , no solo `value1` . Este comportamiento difiere del de las uniones discriminadas. Esto se debe a que las enumeraciones siempre tienen el atributo [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) .

En el código siguiente se muestra la declaración y el uso de una enumeración.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Puede convertir fácilmente las enumeraciones en el tipo subyacente mediante el operador adecuado, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Los tipos enumerados pueden tener uno de los siguientes tipos subyacentes: `sbyte` , `byte` , `int16` , `uint16` , `int32` , `uint32` , `int64` ,, `uint16` `uint64` y `char` . Los tipos de enumeración se representan en el .NET Framework como tipos que se heredan de `System.Enum` , que a su vez se hereda de `System.ValueType` . Por lo tanto, son tipos de valor que se encuentran en la pila o insertados en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración. Esto es importante cuando la coincidencia de patrones en los valores de enumeración, porque tiene que proporcionar un patrón que detecte los valores sin nombre.

La `enum` función de la biblioteca de F # se puede usar para generar un valor de enumeración, incluso un valor distinto de uno de los valores con nombre predefinidos. La función se usa `enum` como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

La `enum` función predeterminada funciona con el tipo `int32` . Por lo tanto, no se puede utilizar con tipos de enumeración que tienen otros tipos subyacentes. En su lugar, use lo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Además, los casos de enumeración siempre se emiten como `public` . Esto es para que se alineen con C# y el resto de la plataforma .NET.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Conversiones](casting-and-conversions.md)
