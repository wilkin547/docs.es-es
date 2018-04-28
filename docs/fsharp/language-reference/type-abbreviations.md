---
title: Abreviaturas de tipo (F#)
description: 'Obtenga información acerca de abreviaturas de tipo de F # para proporcionar un nombre más descriptivo a un tipo con el fin de facilitar la lectura del código.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bf17ee9795947fdc11fe958f09d52f5730b95bf8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="type-abbreviations"></a>Abreviaturas de tipo

A *abreviatura de tipo* es un alias o nombre alternativo para un tipo.

## <a name="syntax"></a>Sintaxis

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a>Comentarios
Puede utilizar las abreviaturas de tipo para asignar un nombre más significativo, de un tipo con el fin de facilitar la lectura del código. También puede usar para crear un nombre fácil de usar para un tipo que en caso contrario, es difícil de escribir. Además, puede utilizar las abreviaturas de tipo para que sea más fácil cambiar un tipo subyacente sin modificar todo el código que utiliza el tipo. La siguiente es una abreviatura de tipo simple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Abreviaturas de tipo pueden incluir parámetros genéricos, como en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

En el código anterior, `Transform` es una abreviatura de tipo que representa una función que toma un único argumento de cualquier tipo y que devuelve un valor único de dicho tipo.

Abreviaturas de tipo no se conservan en el código de MSIL de .NET Framework. Por lo tanto, cuando se usa un ensamblado de F # desde otro lenguaje de .NET Framework, debe utilizar el nombre del tipo subyacente de una abreviatura de tipo.

Abreviaturas de tipo también pueden utilizarse en las unidades de medida. Para obtener más información, consulte [unidades de medida](units-of-measure.md).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

