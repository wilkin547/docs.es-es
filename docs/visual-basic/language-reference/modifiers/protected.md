---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 40dda40f68e535380a82a241e3ccd383b0c9809f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536300"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Un modificador de acceso de miembro que especifica que uno o varios elementos de programación declaran están accesibles únicamente desde dentro de su propia clase o desde una clase derivada.  
  
## <a name="remarks"></a>Comentarios  
 A veces un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento. Sin embargo, si se puede heredar la clase y esperar una jerarquía de clases derivadas, podría ser necesario para estas clases derivadas tener acceso a los datos o código. En tal caso, desea que el elemento para que sea accesible desde la clase base y todas las clases derivadas. Para limitar el acceso a un elemento de esta manera, puede declarar con `Protected`.  

> [!NOTE]
> El `Protected` modificador de acceso se puede combinar con otros dos modificadores:
> - El [Protected Friend](protected-friend.md) modificador hace que un miembro de clase que sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase. 
> - El [Private Protected](private-protected.md) modificador hace que un miembro de clase sea accesible por tipos derivados, pero solo dentro de su ensamblado de contenedor.
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Puede usar `Protected` sólo en el nivel de clase. Esto significa que el contexto de declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.  

## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Todo el código en una clase puede tener acceso a sus elementos. Código de cualquier clase que derive de una clase base puede tener acceso a todas las `Protected` elementos de la clase base. Esto es cierto para todas las generaciones de derivación. Esto significa que puede tener acceso una clase `Protected` elementos de la clase base de la clase base y así sucesivamente.  
  
     Acceso protegido no es un supraconjunto ni un subconjunto de acceso de confianza.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
