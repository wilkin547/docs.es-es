---
title: El descriptor de acceso 'Set' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3cf828eb5f11090a74a65388e2b89a191046a456
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162250"
---
# <a name="bc31102-set-accessor-of-property-propertyname-is-not-accessible"></a>BC31102: \<propertyname> no se puede acceder al descriptor de acceso ' Set ' de la propiedad ' '

Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso al procedimiento de la propiedad `Set` .

 Si la [instrucción set](../statements/set-statement.md) está marcada con un nivel de acceso más restrictivo que su [instrucción Property](../statements/property-statement.md), se podría producir un error al intentar establecer el valor de la propiedad en los casos siguientes:

- La `Set` instrucción está marcada como [privada](../modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.

- La `Set` instrucción se marca como [protegida](../modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.

- La `Set` instrucción está marcada como [Friend](../modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.

 **Identificador de error:** BC31102

## <a name="to-correct-this-error"></a>Para corregir este error

- Si tiene el control del código fuente que define la propiedad, considere la posibilidad de declarar el `Set` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.

- Si no tiene control sobre el código fuente que define la propiedad o si debe restringir el `Set` nivel de acceso del procedimiento más que la propiedad, intente trasladar la instrucción que establece el valor de la propiedad a una región de código que tenga un mejor acceso a la propiedad.

## <a name="see-also"></a>Vea también

- [Procedimientos de propiedad](../../programming-guide/language-features/procedures/property-procedures.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
