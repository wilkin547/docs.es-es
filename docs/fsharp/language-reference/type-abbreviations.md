---
title: Abreviaturas de tipo (F#)
description: 'Obtenga información acerca de abreviaturas de tipo de F # para proporcionar un nombre más descriptivo a un tipo con el fin de facilitar la lectura del código.'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058963"
---
# <a name="type-abbreviations"></a>Abreviaturas de tipo

A *abreviatura de tipo* es un alias o nombre alternativo para un tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Comentarios
Puede utilizar las abreviaturas de tipo para asignar un nombre más significativo, de un tipo con el fin de facilitar la lectura del código. También puede usar para crear un nombre fácil de usar para un tipo que en caso contrario, es difícil de escribir. Además, puede utilizar las abreviaturas de tipo para que sea más fácil cambiar un tipo subyacente sin modificar todo el código que utiliza el tipo. La siguiente es una abreviatura de tipo simple.

Accesibilidad de abreviaturas de tipo de valor predeterminado es `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Abreviaturas de tipo pueden incluir parámetros genéricos, como en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

En el código anterior, `Transform` es una abreviatura de tipo que representa una función que toma un único argumento de cualquier tipo y que devuelve un valor único de dicho tipo.

Abreviaturas de tipo no se conservan en el código de MSIL de .NET Framework. Por lo tanto, cuando se usa un ensamblado de F # desde otro lenguaje de .NET Framework, debe utilizar el nombre del tipo subyacente de una abreviatura de tipo.

Abreviaturas de tipo también pueden utilizarse en las unidades de medida. Para obtener más información, consulte [unidades de medida](units-of-measure.md).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

