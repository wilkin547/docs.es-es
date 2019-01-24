---
title: Procedimiento Hacer referencia a un miembro de enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: efaaecb231b340798012206a0f23fde0ad4cdbeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602005"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Procedimiento Hacer referencia a un miembro de enumeración (Visual Basic)
Las enumeraciones proporcionan una forma cómoda para trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres. Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.  
  
 Se puede evitar usar nombres completos con el `Imports` instrucción. Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>Para hacer referencia a un miembro de enumeración  
  
-   Calificar el nombre del miembro con la enumeración. Por ejemplo, en el ejemplo siguiente se asigna el `Saturday` miembro de la `FirstDayOfWeek` enumeración a la variable `DayValue`.  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-refer-to-an-enumeration-member_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Cómo: Determinar la cadena asociada con un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
