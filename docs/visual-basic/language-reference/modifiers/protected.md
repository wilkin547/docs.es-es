---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro de su propia clase o desde una clase derivada.  
  
## <a name="remarks"></a>Comentarios  
 A veces un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento. Sin embargo, si se puede heredar la clase y se espera que una jerarquía de clases derivadas, podría ser necesario para estas clases derivadas tener acceso a los datos o código. En este caso, desea que el elemento que se va a estar accesible desde la clase base y de todas las clases derivadas. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected`.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Puede usar `Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.  
  
-   **Modificadores combinados.** Puede usar el `Protected` modificador junto con el [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modificador en la misma declaración. Esta combinación hace que los elementos declarados accesible desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas. Puede especificar `Protected Friend` solo en los miembros de clases.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Todo el código en una clase puede tener acceso a sus elementos. Código de cualquier clase que deriva de una clase base puede tener acceso a toda la `Protected` elementos de la clase base. Esto es cierto para todas las generaciones de derivación. Esto significa que puede tener acceso una clase `Protected` elementos de la clase base de la clase base y así sucesivamente.  
  
     Acceso protegido no es un supraconjunto ni un subconjunto de acceso de confianza.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Protected` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
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
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
