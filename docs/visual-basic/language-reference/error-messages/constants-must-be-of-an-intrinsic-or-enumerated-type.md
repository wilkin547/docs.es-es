---
description: 'Más información sobre: BC30424: las constantes deben ser de tipo intrínseco o enumerado, no una clase, una estructura, un parámetro de tipo o un tipo de matriz'
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e9765d78ff671d6b99f47242509b1c3b4560c029
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796735"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>BC30424: las constantes deben ser de un tipo intrínseco o enumerado, no una clase, una estructura, un parámetro de tipo o un tipo de matriz

Ha intentado declarar una constante como una clase, una estructura o un tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.

 Las constantes deben ser de un tipo intrínseco ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` o `UShort` ) o un `Enum` tipo basado en uno de los tipos enteros.

 **Identificador de error:** BC30424

## <a name="to-correct-this-error"></a>Para corregir este error

1. Declare la constante como un tipo o intrínseco `Enum` .

2. Una constante también puede ser un valor especial, como `True` , `False` o `Nothing` . El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.

## <a name="see-also"></a>Vea también

- [Constantes y enumeraciones](../constants-and-enumerations.md)
- [Tipo de datos](../../programming-guide/language-features/data-types/index.md)
- [Tipo de datos](../data-types/index.md)
