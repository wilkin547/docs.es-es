---
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083927"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
Ha intentado declarar una constante como una clase, estructura o tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.  
  
 Las constantes deben ser de un tipo intrínseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basado en uno de los tipos enteros.  
  
 **Identificador de error:** BC30424  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declare la constante como intrínseco o `Enum` tipo.  
  
2.  Una constante puede ser también un valor especial como `True`, `False`, o `Nothing`. El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.  
  
## <a name="see-also"></a>Vea también  
 [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
