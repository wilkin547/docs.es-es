---
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: a9bbf27615233f4282e481710a0234b2fa589f63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874561"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz

Ha intentado declarar una constante como una clase, una estructura o un tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.  
  
 Las constantes deben ser de un tipo intrínseco ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` o `UShort` ) o un `Enum` tipo basado en uno de los tipos enteros.  
  
 **Identificador de error:** BC30424  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Declare la constante como un tipo o intrínseco `Enum` .  
  
2. Una constante también puede ser un valor especial, como `True` , `False` o `Nothing` . El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.  
  
## <a name="see-also"></a>Consulte también

- [Constantes y enumeraciones](../constants-and-enumerations.md)
- [Tipo de datos](../../programming-guide/language-features/data-types/index.md)
- [Tipo de datos](../data-types/index.md)
