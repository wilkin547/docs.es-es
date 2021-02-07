---
description: 'Más información acerca de: protected Friend (Visual Basic)'
title: Protected Friend
ms.date: 05/10/2018
f1_keywords:
- vb.ProtectedFriend
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: dcc8fd2b1aa99f910f002ac05178d379532fb73d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700980"
---
# <a name="protected-friend-visual-basic"></a>Friend protegido (Visual Basic)

La combinación de palabras claves `Protected Friend` es un modificador de acceso de miembro. Confiere acceso de [confianza](friend.md) y acceso [protegido](protected.md) en los elementos declarados, por lo que son accesibles desde cualquier lugar del mismo ensamblado, desde su propia clase y desde las clases derivadas. Solo se puede especificar `Protected Friend` en miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no se pueden heredar.

> [!NOTE]
> En Visual Studio, al seleccionar la ayuda F1 en se `protected friend` proporciona ayuda para [Protected](protected.md) o [Friend](friend.md). El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

**Contexto de declaración.** Solo se puede usar `Protected Friend` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

## <a name="see-also"></a>Vea también

- [Público](public.md)
- [Protegido](protected.md)
- [Friend](friend.md)
- [Privado](private.md)
- [Private Protected](./private-protected.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
