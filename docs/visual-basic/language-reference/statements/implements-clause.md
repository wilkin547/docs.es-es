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
ms.openlocfilehash: 46ab1a1148e8d73d91293aedfc407e5efdc7cfb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404568"
---
# <a name="implements-clause-visual-basic"></a>Implements (Cláusula, Visual Basic)
Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.  
  
## <a name="remarks"></a>Observaciones  
La `Implements` palabra clave no es lo mismo que la [instrucción Implements](implements-statement.md). La instrucción se usa `Implements` para especificar que una clase o estructura implementa una o más interfaces y, a continuación, para cada miembro, se usa la `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.

Si una clase o estructura implementa una interfaz, debe incluir la `Implements` instrucción inmediatamente después de la instrucción de [clase](class-statement.md) o [instrucción de estructura](structure-statement.md), y debe implementar todos los miembros definidos por la interfaz.

## <a name="reimplementation"></a>Reimplementación  
En una clase derivada, puede volver a implementar un miembro de interfaz que la clase base ya ha implementado. Esto no es lo mismo que reemplazar el miembro de clase base en los siguientes aspectos:

- No es necesario [reemplazar](../modifiers/overridable.md) el miembro de la clase base para que se pueda volver a implementar.
- Puede volver a implementar el miembro con un nombre diferente.

La `Implements` palabra clave se puede usar en los contextos siguientes:

- [Event (Instrucción)](event-statement.md)
- [Instrucción Function](function-statement.md)
- [Property Statement](property-statement.md)
- [Instrucción Sub](sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Implements (Instrucción)](implements-statement.md)
- [Instrucción Interface](interface-statement.md)
- [Instrucción Class](class-statement.md)
- [Structure (Instrucción)](structure-statement.md)
