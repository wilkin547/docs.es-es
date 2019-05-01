---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051876"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Especifica que uno o varios elementos de programación declarados no tienen acceso restricciones.  
  
## <a name="remarks"></a>Comentarios  
 Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación para ser accesibles para cualquier código que interactúa con el ensamblado. Para otorgar este acceso ilimitado en un elemento, puede declarar con `Public`.  
  
 Acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él. Tenga en cuenta que el nivel de acceso de un elemento se declara dentro de una interfaz, módulo, clase o estructura el valor predeterminado es `Public` si no se declara en caso contrario.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Puede usar `Public` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que el contexto de declaración de un `Public` elemento debe ser un archivo de código fuente, el espacio de nombres, la interfaz, el módulo, la clase o estructura y no puede ser un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Puede tener acceso todo el código que puede tener acceso a un módulo, clase o estructura su `Public` elementos.  
  
- **Acceso predeterminado.** Variables locales dentro de una procedimiento de forma predeterminada al acceso público y no pueden utilizar cualquier modificador de acceso en ellas.  
  
- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
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
