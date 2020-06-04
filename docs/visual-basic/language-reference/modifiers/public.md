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
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415354"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Especifica que uno o varios elementos de programación declarados no tienen restricciones de acceso.  
  
## <a name="remarks"></a>Observaciones  
 Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación sean accesibles por cualquier código que interopere con el ensamblado. Para atribuir este acceso ilimitado en un elemento, puede declararlo con `Public` .  
  
 El acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él. Tenga en cuenta que el nivel de acceso de un elemento declarado dentro de una interfaz, módulo, clase o estructura tiene como valor predeterminado `Public` si no lo declara de otro modo.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Solo se puede usar `Public` en el nivel de módulo, interfaz o espacio de nombres. Esto significa que el contexto de la declaración de un `Public` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura, y no puede ser un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Todo el código que puede tener acceso a un módulo, clase o estructura puede tener acceso a sus `Public` elementos.  
  
- **Acceso predeterminado.** Las variables locales dentro de un procedimiento tienen como valor predeterminado el acceso público y no se pueden usar modificadores de acceso en ellas.  
  
- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Public` se puede utilizar en los contextos siguientes:  
  
 [Instrucción Class](../statements/class-statement.md)  
  
 [Instrucción Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Delegate (Instrucción)](../statements/delegate-statement.md)  
  
 [Instrucción Dim](../statements/dim-statement.md)  
  
 [Instrucción Enum](../statements/enum-statement.md)  
  
 [Event (Instrucción)](../statements/event-statement.md)  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Instrucción Interface](../statements/interface-statement.md)  
  
 [Module (Instrucción)](../statements/module-statement.md)  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure (Instrucción)](../statements/structure-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Contra](protected.md)
- [Respecto](friend.md)
- [Privado](private.md)
- [Privado protegido](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
