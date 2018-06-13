---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306550"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

El `Protected Friend` combinación de palabra clave es un modificador de acceso de miembro. Confiere ambos [Friend](friend.md) acceso y [Protected](protected.md) acceso a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas. Puede especificar `Protected Friend` sólo en los miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no puede heredarse.

> [!NOTE]
> En Visual Studio, seleccione Ayuda de F1 en `protected friend` proporciona ayuda para cualquiera [protegido](protected.md) o [friend](friend.md). El IDE elige el token único en el cursor en lugar de la palabra compuesta.

## <a name="rules"></a>Reglas

- **Contexto de la declaración.** Puede usar `Protected Friend` en el nivel de clase. Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento. 


## <a name="see-also"></a>Vea también

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Privado protegido](./private-protected.md)   
[Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
