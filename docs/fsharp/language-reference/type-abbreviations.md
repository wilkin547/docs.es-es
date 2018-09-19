---
title: Abreviaturas de tipo (F#)
description: 'Obtenga información sobre las abreviaturas de tipo de F # para proporcionar un nombre más significativo a un tipo con el fin de facilitar la lectura del código.'
ms.date: 05/16/2016
ms.openlocfilehash: 259cd6c84e22fc7c98e08255d3e0ded5b87af352
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288334"
---
# <a name="type-abbreviations"></a>Abreviaturas de tipo

Un *abreviatura de tipo* es un alias o nombre alternativo para un tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Comentarios

Puede usar las abreviaturas de tipo para asignar un nombre más significativo, de un tipo con el fin de facilitar la lectura del código. También puede usar para crear un nombre fácil de usar para un tipo que en caso contrario, es difícil de escribir. Además, puede usar las abreviaturas de tipo para que sea más fácil cambiar un tipo subyacente sin modificar todo el código que utiliza el tipo. La siguiente es una abreviatura de tipo simple.

Accesibilidad de abreviaturas de tipo de valor predeterminado es `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Abreviaturas de tipo pueden incluir parámetros genéricos, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

En el código anterior, `Transform` es una abreviatura del tipo que representa una función que toma un único argumento de cualquier tipo y que devuelve un valor único de ese mismo tipo.

Abreviaturas de tipo no se conservan en el código MSIL de .NET Framework. Por lo tanto, cuando se usa un ensamblado de F # desde otro lenguaje de .NET Framework, debe usar el nombre de tipo subyacente para una abreviatura de tipo.

Abreviaturas de tipo también pueden usarse en unidades de medida. Para obtener más información, consulte [unidades de medida](units-of-measure.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
