---
title: 'Cómo: Agrupar valores de constantes relacionadas (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 320373116ad4d61293690353fce6b7b152e79a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Cómo: Agrupar valores de constantes relacionadas (Visual Basic)
Una enumeración es la mejor manera de agrupar constantes relacionadas. Cree una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo. Para obtener más información, consulte [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Al grupo de valores de constantes relacionadas  
  
1.  Escriba una declaración que incluya un nivel de acceso del código, la `Enum` palabra clave y un nombre válido. Este ejemplo se crea el `Private` enumeración, `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  Defina las constantes en la enumeración. Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
