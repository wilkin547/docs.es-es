---
title: Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: c8480c6fab2bff931950ebc21d0a8affe3c41c66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774821"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'
No se puede convertir el valor de tipo 'tipo1' a 'tipo2'. Puede usar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<Elementoprimario >'.  
  
 Se intentó convertir implícitamente un literal XML a un tipo específico. El literal XML no se puede convertir implícitamente al tipo especificado.  
  
 **Identificador de error:** BC31194  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`. Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Convert>
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
