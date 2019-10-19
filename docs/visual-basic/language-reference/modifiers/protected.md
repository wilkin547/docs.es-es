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
ms.openlocfilehash: 8370d15e99a6f7ed0868441a4e44360fb258be13
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583070"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Modificador de acceso de miembro que especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro de su propia clase o desde una clase derivada.

## <a name="remarks"></a>Comentarios

A veces, un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento. Sin embargo, si la clase es heredable y espera una jerarquía de clases derivadas, podría ser necesario que estas clases derivadas tengan acceso a los datos o al código. En tal caso, desea que el elemento sea accesible tanto desde la clase base como desde todas las clases derivadas. Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected`.

> [!NOTE]
> El modificador de acceso `Protected` se puede combinar con otros dos modificadores:
>
> - El modificador [Friend protegido](protected-friend.md) hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase.
> - El modificador [Private Protected](private-protected.md) hace que un miembro de clase sea accesible para los tipos derivados, pero solo dentro del ensamblado que lo contiene.

## <a name="rules"></a>Reglas

**Contexto de declaración.** Solo se puede usar `Protected` en el nivel de clase. Esto significa que el contexto de la declaración de un elemento `Protected` debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Todo el código de una clase puede tener acceso a sus elementos. El código de cualquier clase que deriva de una clase base puede tener acceso a todos los elementos `Protected` de la clase base. Esto es cierto para todas las generaciones de derivación. Esto significa que una clase puede tener acceso a `Protected` elementos de la clase base de la clase base, etc.

     El acceso protegido no es un superconjunto o subconjunto de acceso de confianza.

- **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

El modificador `Protected` se puede utilizar en los contextos siguientes:

- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

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
