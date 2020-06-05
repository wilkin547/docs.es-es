---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 524f03e77e075bef08a1b41b563985de41baacb6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404815"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del contexto de declaración, incluido desde dentro de cualquier tipo contenido.  
  
## <a name="remarks"></a>Observaciones  
 Si un elemento de programación representa la funcionalidad de propiedad o contiene datos confidenciales, normalmente querrá limitar el acceso a él lo máximo posible. Para lograr la limitación máxima, solo se permite el módulo, la clase o la estructura que la define para tener acceso a ella. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private` .  

> [!NOTE]
> También puede usar el modificador de acceso [protegido privado](private-protected.md) , que hace que un miembro sea accesible desde dentro de esa clase y desde las clases derivadas que se encuentran en el ensamblado que lo contiene.

## <a name="rules"></a>Reglas  

- **Contexto de declaración.** Solo se puede usar `Private` en un nivel de módulo. Esto significa que el contexto de la declaración de un `Private` elemento debe ser un módulo, una clase o una estructura, y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz o un procedimiento.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Todo el código dentro de un contexto de declaración puede tener acceso a sus `Private` elementos. Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración. Ningún código fuera del contexto de la declaración puede tener acceso a sus `Private` elementos.  
  
- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Private` se puede utilizar en los contextos siguientes:  
  
 [Instrucción Class](../statements/class-statement.md)  
  
 [Instrucción Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Delegate (Instrucción)](../statements/delegate-statement.md)  
  
 [Instrucción Dim](../statements/dim-statement.md)  
  
 [Instrucción Enum](../statements/enum-statement.md)  
  
 [Event (Instrucción)](../statements/event-statement.md)  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Instrucción Interface](../statements/interface-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure (Instrucción)](../statements/structure-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Público](public.md)
- [Contra](protected.md)
- [Respecto](friend.md)
- [Privado protegido](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
