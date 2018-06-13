---
title: Valor de tipo &#39;type1&#39; no se puede convertir a &#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602767"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>Valor de tipo &#39;type1&#39; no se puede convertir a &#39;type2&#39;
No se puede convertir el valor de tipo 'tipo1' a 'tipo2'. Puede utilizar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<Elementoprimario >'.  
  
 Se intentó convertir implícitamente un literal XML a un tipo específico. El literal XML no se puede convertir implícitamente al tipo especificado.  
  
 **Id. de error:** BC31194  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`. Use la función `CType` , otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Convert>  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
