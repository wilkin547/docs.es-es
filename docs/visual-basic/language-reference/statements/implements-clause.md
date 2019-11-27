---
title: Cláusula Implements
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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345870"
---
# <a name="implements-clause-visual-basic"></a>Implements (Cláusula, Visual Basic)
Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.  
  
## <a name="remarks"></a>Comentarios  
La palabra clave `Implements` no es igual que la [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Use la instrucción `Implements` para especificar que una clase o estructura implementa una o más interfaces y, a continuación, para cada miembro, use la palabra clave `Implements` para especificar qué interfaz y qué miembro implementa.

Si una clase o estructura implementa una interfaz, debe incluir la instrucción `Implements` inmediatamente después de la instrucción de [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [instrucción de estructura](../../../visual-basic/language-reference/statements/structure-statement.md), y debe implementar todos los miembros definidos por la interfaz.

## <a name="reimplementation"></a>Reimplementación  
En una clase derivada, puede volver a implementar un miembro de interfaz que la clase base ya ha implementado. Esto no es lo mismo que reemplazar el miembro de clase base en los siguientes aspectos:

- No es necesario [reemplazar](../../../visual-basic/language-reference/modifiers/overridable.md) el miembro de la clase base para que se pueda volver a implementar.
- Puede volver a implementar el miembro con un nombre diferente.

La palabra clave `Implements` se puede utilizar en los contextos siguientes:

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
