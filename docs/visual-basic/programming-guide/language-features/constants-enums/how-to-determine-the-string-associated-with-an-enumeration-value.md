---
title: 'Cómo: Determinar la cadena asociada a un valor de enumeración (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c14ea61feba7d7d85f9a4fc377aefdd8fa240c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651705"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Cómo: Determinar la cadena asociada a un valor de enumeración (Visual Basic)
El <xref:System.Enum.GetValues%2A> y <xref:System.Enum.GetNames%2A> métodos permiten determinar las cadenas y valores asociados a los miembros de enumeración.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Para determinar la cadena asociada a una enumeración  
  
-   Use la <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de enumeración. Este ejemplo declara una enumeración, `flavorEnum`, a continuación, utiliza el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)
