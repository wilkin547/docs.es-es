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
ms.openlocfilehash: dcd20f21a989c327dcfcf27d5638d500b6e4b6da
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929317"
---
# <a name="implements-clause-visual-basic"></a>Implements (Cláusula, Visual Basic)
Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.  
  
## <a name="remarks"></a>Comentarios  
La `Implements` palabra clave no es lo mismo que la [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md). La `Implements` instrucción se usa para especificar que una clase o estructura implementa una o más interfaces y, a continuación, para cada miembro, se `Implements` usa la palabra clave para especificar qué interfaz y qué miembro implementa.

Si una clase o estructura implementa una interfaz, debe incluir la `Implements` instrucción inmediatamente después de la instrucción de [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [instrucción de estructura](../../../visual-basic/language-reference/statements/structure-statement.md), y debe implementar todos los miembros definidos por la interfaz.

## <a name="reimplementation"></a>Reimplementación  
En una clase derivada, puede volver a implementar un miembro de interfaz que la clase base ya ha implementado. Esto no es lo mismo que reemplazar el miembro de clase base en los siguientes aspectos:

- No es necesario [reemplazar](../../../visual-basic/language-reference/modifiers/overridable.md) el miembro de la clase base para que se pueda volver a implementar.
- Puede volver a implementar el miembro con un nombre diferente.

La `Implements` palabra clave se puede usar en los contextos siguientes:

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
