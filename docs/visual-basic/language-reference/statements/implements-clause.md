---
title: Implements (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implements-clause-visual-basic"></a>Implements (Cláusula, Visual Basic)
Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.  
  
## <a name="remarks"></a>Comentarios  
El `Implements` palabra clave no es el mismo que el [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md). Usa el `Implements` instrucción para especificar que una clase o estructura implementa una o más interfaces, y, a continuación, para cada miembro use el `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.

Si una clase o estructura implementa una interfaz, debe incluir el `Implements` instrucción inmediatamente después de la [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) o [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md), y debe implementar todos los miembros define la interfaz.

## <a name="reimplementation"></a>Segunda implementación  
En una clase derivada, puede volver a implementar a un miembro de interfaz que la clase base ya ha implementado. Esto es diferente de reemplazar al miembro de clase base en los siguientes aspectos:

- No es necesario ser miembro de clase base [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) para ser implementado de nuevo.
- Puede volver a implementar al miembro con un nombre diferente.

El `Implements` palabra clave puede utilizarse en los contextos siguientes:
- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
