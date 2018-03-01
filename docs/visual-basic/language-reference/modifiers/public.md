---
title: Public (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6cd70adf6ec31c56f39d0443d320dd1b00b00d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
No especifica que uno o varios elementos de programación declarados restricciones de acceso.  
  
## <a name="remarks"></a>Comentarios  
 Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación que se va a ser accesibles para cualquier código que interopere con su ensamblado. Para otorgar este acceso ilimitado en un elemento, puede declararlo con `Public`.  
  
 Acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él. Tenga en cuenta que el nivel de acceso de un elemento declarado en una interfaz, módulo, clase o estructura tiene como valor predeterminado `Public` si no se declara en caso contrario.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Puede usar `Public` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que el contexto de la declaración de un `Public` elemento debe ser un archivo de código fuente, el espacio de nombres, la interfaz, el módulo, la clase o estructura y no puede ser un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Puede tener acceso todo el código que puede tener acceso a un módulo, clase o estructura su `Public` elementos.  
  
-   **Acceso predeterminado.** Las variables locales dentro de una procedimiento de forma predeterminada al acceso público y no pueden usar los modificadores de acceso en ellos.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
