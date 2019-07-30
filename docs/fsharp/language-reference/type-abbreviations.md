---
title: Abreviaturas de tipo
description: Obtenga información F# sobre las abreviaturas de tipo para asignar un nombre más significativo a un tipo con el fin de facilitar la lectura del código.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630216"
---
# <a name="type-abbreviations"></a>Abreviaturas de tipo

Una *abreviatura de tipo* es un alias o un nombre alternativo para un tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Comentarios

Puede usar las abreviaturas de tipo para asignar un nombre más significativo a un tipo, con el fin de facilitar la lectura del código. También puede usarlos para crear un nombre fácil de usar para un tipo que, de otro modo, es engorroso de escribir. Además, puede usar las abreviaturas de tipo para facilitar la modificación de un tipo subyacente sin cambiar todo el código que usa el tipo. La siguiente es una abreviatura de tipo simple.

La accesibilidad de las abreviaturas de tipo `public`tiene como valor predeterminado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Las abreviaturas de tipo pueden incluir parámetros genéricos, como en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

En el código anterior, `Transform` es una abreviatura de tipo que representa una función que toma un solo argumento de cualquier tipo y que devuelve un valor único del mismo tipo.

Las abreviaturas de tipo no se conservan en el código MSIL de .NET Framework. Por lo tanto, cuando se F# usa un ensamblado de otro lenguaje .NET Framework, se debe usar el nombre de tipo subyacente para una abreviatura de tipo.

Las abreviaturas de tipo también se pueden usar en unidades de medida. Para obtener más información, consulte [unidades de medida](units-of-measure.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
