---
title: Público
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351291"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Especifica que uno o varios elementos de programación declarados no tienen restricciones de acceso.  
  
## <a name="remarks"></a>Comentarios  
 Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación sean accesibles por cualquier código que interopere con el ensamblado. Para atribuir este acceso ilimitado en un elemento, puede declararlo con `Public`.  
  
 El acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él. Tenga en cuenta que el nivel de acceso de un elemento declarado en una interfaz, módulo, clase o estructura tiene como valor predeterminado `Public` si no lo declara de otro modo.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Solo se puede usar `Public` en el nivel de módulo, interfaz o espacio de nombres. Esto significa que el contexto de la declaración de un elemento `Public` debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura, y no puede ser un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Todo el código que puede tener acceso a un módulo, clase o estructura puede tener acceso a sus elementos `Public`.  
  
- **Acceso predeterminado.** Las variables locales dentro de un procedimiento tienen como valor predeterminado el acceso público y no se pueden usar modificadores de acceso en ellas.  
  
- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Public` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
