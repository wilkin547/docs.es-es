---
title: Procedimiento para agrupar valores de constantes relacionadas
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414445"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Cómo: Agrupar valores de constantes relacionadas (Visual Basic)
Una enumeración es la mejor manera de agrupar constantes relacionadas. Cree una enumeración con la `Enum` instrucción en la sección de declaraciones de una clase o módulo. Para obtener más información, vea [Cómo: declarar una enumeración](how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Para agrupar los valores constantes relacionados  
  
1. Escriba una declaración que incluya un nivel de acceso de código, la `Enum` palabra clave y un nombre válido. En este ejemplo se crea la `Private` enumeración, `temperatureValues` .  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Defina las constantes en la enumeración. En este ejemplo se crea la `Public` enumeración `temperatureValues` y se asignan sus valores.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)
- [Información general sobre las constantes](constants-overview.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md)
