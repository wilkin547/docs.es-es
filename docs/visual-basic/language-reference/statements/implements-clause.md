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
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637770"
---
# <a name="implements-clause-visual-basic"></a>Implements (Cláusula, Visual Basic)
Indica que un miembro de clase o estructura proporciona la implementación de un miembro definido en una interfaz.  
  
## <a name="remarks"></a>Comentarios  
El `Implements` palabra clave no es igual que el [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Usa el `Implements` instrucción para especificar que una clase o estructura implementa una o varias interfaces y, a continuación, para cada miembro que usa el `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.

Si una clase o estructura implementa una interfaz, debe incluir el `Implements` instrucción inmediatamente después de la [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) o [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md), y debe implementar todos los miembros define la interfaz.

## <a name="reimplementation"></a>Reimplementación  
En una clase derivada, puede volver a implementar a un miembro de interfaz que ya ha implementado la clase base. Esto es diferente de reemplazar al miembro de clase base en los siguientes aspectos:

- No es necesario ser miembro de clase base [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) para ser implementado de nuevo.
- Puede volver a implementar al miembro con un nombre diferente.

El `Implements` palabra clave puede utilizarse en los contextos siguientes:
- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
