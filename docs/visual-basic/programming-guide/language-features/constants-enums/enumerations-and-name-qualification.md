---
description: 'Más información acerca de: enumeraciones y calificación de nombres (Visual Basic)'
title: Enumeraciones y calificación de nombres
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
ms.openlocfilehash: 83f5b894dad821fea920386be905de0b51f9c42f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100477481"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Enumeraciones y calificación de nombres (Visual Basic)

Normalmente, cuando se hace referencia a un miembro de una enumeración, se debe calificar el nombre del miembro con el nombre de la enumeración. Por ejemplo, para hacer referencia al `Sunday` miembro de la `Days` enumeración, usaría la siguiente sintaxis:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Usar la instrucción Imports  

 Puede evitar el uso de nombres completos agregando una `Imports` instrucción a la sección de declaraciones de espacio de nombres del código, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Una `Imports` instrucción importa nombres de espacios de nombres de ensamblados y proyectos a los que se hace referencia y desde dentro del mismo proyecto que el módulo en el que aparece la instrucción. Una vez agregada esta instrucción, puede hacer referencia a los miembros de enumeración sin calificación, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Al organizar conjuntos de constantes relacionadas en las enumeraciones, puede utilizar los mismos nombres de constantes en contextos diferentes. Por ejemplo, puede usar los mismos nombres para las constantes Weekday en las `Days` `WorkDays` enumeraciones y. Si usa la `Imports` instrucción con las enumeraciones, debe tener cuidado de evitar referencias ambiguas. Considere el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Suponiendo que `Monday` es miembro de la `Days` enumeración y de la `Workdays` enumeración, este código genera un error del compilador. Para evitar referencias ambiguas al hacer referencia a una constante individual, califique el nombre de la constante con su enumeración. El código siguiente hace referencia a las `Saturday` constantes de las `Days` `WorkDays` enumeraciones y.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Consulte también

- [Constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md)
- [Cómo: Declarar una enumeración](how-to-declare-enumerations.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedimiento para determinar la cadena asociada a un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Instrucción Enum](../../../language-reference/statements/enum-statement.md)
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Tipo de datos](../../../language-reference/data-types/index.md)
