---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151780"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

La combinación de palabras claves `Protected Friend` es un modificador de acceso de miembro. Concede tanto [Friend](friend.md) acceso y [Protected](protected.md) acceso a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas. Puede especificar `Protected Friend` solo en los miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no se puede heredar.

> [!NOTE]
> En Visual Studio, seleccione Ayuda de F1 en `protected friend` proporciona ayuda para cualquiera [protegido](protected.md) o [friend](friend.md). El IDE elige el token solo bajo el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Puede usar `Protected Friend` sólo en el nivel de clase. Esto significa que el contexto de declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento. 

## <a name="see-also"></a>Vea también

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private protegida](./private-protected.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
