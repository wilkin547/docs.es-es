---
description: 'Más información acerca de cómo: determinar la cadena asociada a un valor de enumeración (Visual Basic)'
title: Procedimiento para determinar la cadena asociada a un valor de enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 391cb097fa8163f7131cc30f85f8a4f85ba826a4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471609"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Cómo: Determinar la cadena asociada a un valor de enumeración (Visual Basic)

Los <xref:System.Enum.GetValues%2A> <xref:System.Enum.GetNames%2A> métodos y permiten determinar las cadenas y los valores asociados a los miembros de enumeración.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Para determinar la cadena asociada a una enumeración  
  
- Use el <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de la enumeración. En este ejemplo se declara una enumeración, `flavorEnum` y, a continuación, se usa el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Cómo: Declarar una enumeración](how-to-declare-enumerations.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)
- [Instrucción Enum](../../../language-reference/statements/enum-statement.md)
