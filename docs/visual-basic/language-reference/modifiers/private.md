---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347915"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del contexto de declaración, incluido desde dentro de cualquier tipo contenido.  
  
## <a name="remarks"></a>Notas  
 Si un elemento de programación representa la funcionalidad de propiedad o contiene datos confidenciales, normalmente querrá limitar el acceso a él lo máximo posible. Para lograr la limitación máxima, solo se permite el módulo, la clase o la estructura que la define para tener acceso a ella. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private`.  

> [!NOTE]
> También puede usar el modificador de acceso [protegido privado](private-protected.md) , que hace que un miembro sea accesible desde dentro de esa clase y desde las clases derivadas que se encuentran en el ensamblado que lo contiene.

## <a name="rules"></a>reglas  

- **Contexto de declaración.** Solo se puede usar `Private` en un nivel de módulo. Esto significa que el contexto de la declaración de un elemento `Private` debe ser un módulo, una clase o una estructura, y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz o un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Todo el código dentro de un contexto de declaración puede tener acceso a sus elementos `Private`. Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración. Ningún código fuera del contexto de la declaración puede tener acceso a sus elementos `Private`.  
  
- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Private` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
