---
description: 'Más información acerca de: protected (Visual Basic)'
title: Protegido
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
ms.openlocfilehash: 74a695e7c8ff06543a7118c935365e31af258171
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700941"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Modificador de acceso de miembro que especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro de su propia clase o desde una clase derivada.

## <a name="remarks"></a>Observaciones

A veces, un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento. Sin embargo, si la clase es heredable y espera una jerarquía de clases derivadas, podría ser necesario que estas clases derivadas tengan acceso a los datos o al código. En tal caso, desea que el elemento sea accesible tanto desde la clase base como desde todas las clases derivadas. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected` .

> [!NOTE]
> El `Protected` modificador de acceso se puede combinar con otros dos modificadores:
>
> - El modificador [Friend protegido](protected-friend.md) hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase.
> - El modificador [Private Protected](private-protected.md) hace que un miembro de clase sea accesible para los tipos derivados, pero solo dentro del ensamblado que lo contiene.

## <a name="rules"></a>Reglas

**Contexto de declaración.** Solo se puede usar `Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código de una clase puede tener acceso a sus elementos. El código de cualquier clase que deriva de una clase base puede tener acceso a todos los `Protected` elementos de la clase base. Esto es cierto para todas las generaciones de derivación. Esto significa que una clase puede tener acceso a los `Protected` elementos de la clase base de la clase base, etc.

     El acceso protegido no es un superconjunto o subconjunto de acceso de confianza.

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

El modificador `Protected` se puede utilizar en los contextos siguientes:

- [Instrucción Class](../statements/class-statement.md)

- [Instrucción Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Delegate (Instrucción)](../statements/delegate-statement.md)

- [Instrucción Dim](../statements/dim-statement.md)

- [Instrucción Enum](../statements/enum-statement.md)

- [Event (Instrucción)](../statements/event-statement.md)

- [Instrucción Function](../statements/function-statement.md)

- [Instrucción Interface](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Structure (Instrucción)](../statements/structure-statement.md)

- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Público](public.md)
- [Friend](friend.md)
- [Privado](private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
