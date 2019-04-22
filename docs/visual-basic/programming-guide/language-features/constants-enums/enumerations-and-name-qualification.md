---
title: Enumeraciones y calificación de nombres (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: f0a806b040720cf6682f8a72025a0590dd4d91f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818441"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Enumeraciones y calificación de nombres (Visual Basic)
Normalmente, cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración. Por ejemplo, para hacer referencia a la `Sunday` miembro de su `Days` enumeración, usaría la sintaxis siguiente:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Mediante la instrucción Imports  
 Se puede evitar usar nombres completos mediante la adición de un `Imports` instrucción en la sección de declaraciones de espacio de nombres del código, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Un `Imports` instrucción importa los espacios de nombres de ensamblados y proyectos que se hace referencia y desde el mismo proyecto que el módulo en el que aparece la instrucción. Una vez agregada esta instrucción, se puede hacer referencia a los miembros de enumeración sin calificación, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Al organizar conjuntos de constantes relacionadas en enumeraciones, puede usar los mismos nombres de constantes en contextos diferentes. Por ejemplo, puede usar los mismos nombres para las constantes de día de la semana en el `Days` y `WorkDays` enumeraciones. Si usas el `Imports` instrucción con las enumeraciones, debe tener cuidado para evitar referencias ambiguas. Considere el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Suponiendo que `Monday` es un miembro de la `Days` enumeración y `Workdays` enumeración, este código genera un error del compilador. Para evitar referencias ambiguas Cuando se hace referencia a una constante individual, califique el nombre de constante con su enumeración. El código siguiente hace referencia a la `Saturday` constantes en el `Days` y `WorkDays` enumeraciones.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Vea también

- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Cómo: Hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Cómo: Determinar la cadena asociada con un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
