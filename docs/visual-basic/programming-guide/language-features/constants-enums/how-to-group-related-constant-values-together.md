---
title: Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 63475487c8a35f5b306b28d4e7097324bef00d85
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977830"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)
Una enumeración es la mejor manera de agrupar constantes relacionadas. Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo. Para obtener más información, vea [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Al grupo de valores de constantes relacionadas  
  
1.  Escriba una declaración que incluye un nivel de acceso del código, el `Enum` palabra clave y un nombre válido. Este ejemplo se crea el `Private` enumeración, `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  Defina las constantes en la enumeración. Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Cómo: Hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
