---
title: Procedimiento Determinar la cadena asociada con un valor de enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690194"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Procedimiento Determinar la cadena asociada con un valor de enumeración (Visual Basic)
El <xref:System.Enum.GetValues%2A> y <xref:System.Enum.GetNames%2A> métodos permiten determinar las cadenas y valores asociados a los miembros de enumeración.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Para determinar la cadena asociada a una enumeración  
  
-   Use el <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de enumeración. En este ejemplo declara una enumeración, `flavorEnum`, a continuación, usa el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Cómo: Hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)
