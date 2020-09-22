---
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870239"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'

El valor de tipo ' tipo1 ' no se puede convertir en ' Type2 '. Puede usar la propiedad ' value ' para obtener el valor de cadena del primer elemento de ' \<parentElement> '.  
  
 Se intentó convertir implícitamente un literal XML a un tipo específico. El literal XML no se puede convertir implícitamente al tipo especificado.  
  
 **Identificador de error:** BC31194  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`. Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Convert>
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Literales XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
