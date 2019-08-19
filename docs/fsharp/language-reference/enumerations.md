---
title: Enumeraciones
description: Aprenda a usar F# enumeraciones en lugar de literales para que el código sea más legible y fácil de mantener.
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630340"
---
# <a name="enumerations"></a>Enumeraciones

Las enumeraciones, también conocidascomo enumeraciones,, son tipos enteros donde las etiquetas se asignan a un subconjunto de los valores. Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.

## <a name="syntax"></a>Sintaxis

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Comentarios

Una enumeración es muy similar a una Unión discriminada que tiene valores simples, con la excepción de que se pueden especificar los valores. Los valores suelen ser enteros que comienzan en 0 o 1, o enteros que representan posiciones de bits. Si una enumeración está pensada para representar posiciones de bits, debe usar también el atributo [Flags](xref:System.FlagsAttribute).

El tipo subyacente de la enumeración se determina a partir del literal que se utiliza, de modo que, por ejemplo, puede usar literales con un sufijo, `1u`como `2u`,, etc., para un tipo entero (`uint32`) sin signo.

Cuando se hace referencia a los valores con nombre, debe usar el nombre del tipo de enumeración como calificador, es decir `enum-name.value1`,, no `value1`solo. Este comportamiento difiere del de las uniones discriminadas. Esto se debe a que las enumeraciones siempre tienen el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) .

En el código siguiente se muestra la declaración y el uso de una enumeración.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Puede convertir fácilmente las enumeraciones en el tipo subyacente mediante el operador adecuado, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Los tipos enumerados pueden tener uno de los siguientes tipos subyacentes `byte`: `int16` `sbyte`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`,, `char`y. Los tipos de enumeración se representan en el .NET Framework como tipos que `System.Enum`se heredan de, que a `System.ValueType`su vez se hereda de. Por lo tanto, son tipos de valor que se encuentran en la pila o insertados en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración. Esto es importante cuando la coincidencia de patrones en los valores de enumeración, porque tiene que proporcionar un patrón que detecte los valores sin nombre.

La `enum` función de la F# biblioteca se puede usar para generar un valor de enumeración, incluso un valor distinto de uno de los valores con nombre predefinidos. La `enum` función se usa como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

La función `enum` predeterminada funciona con el `int32`tipo. Por lo tanto, no se puede utilizar con tipos de enumeración que tienen otros tipos subyacentes. En su lugar, use lo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Además, los casos de enumeración siempre se emiten como `public`. Esto es para que se alineen C# con y el resto de la plataforma .net.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Conversiones](casting-and-conversions.md)
