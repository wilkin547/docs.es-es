---
title: El descriptor de acceso 'Get' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: bd6830e16ba3d1f76c61519b4456832a2efec716
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162913"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a>BC31103: \<propertyname> no se puede acceder al descriptor de acceso ' get ' de la propiedad ' '

Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso al procedimiento de la propiedad `Get` .

 Si la [instrucción Get](../statements/get-statement.md) está marcada con un nivel de acceso más restrictivo que su [instrucción Property](../statements/property-statement.md), se podría producir un error al intentar leer el valor de propiedad en los casos siguientes:

- La `Get` instrucción está marcada como [privada](../modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.

- La `Get` instrucción se marca como [protegida](../modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.

- La `Get` instrucción está marcada como [Friend](../modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.

 **Identificador de error:** BC31103

## <a name="to-correct-this-error"></a>Para corregir este error

- Si tiene el control del código fuente que define la propiedad, considere la posibilidad de declarar el `Get` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.

- Si no tiene control sobre el código fuente que define la propiedad o si debe restringir el `Get` nivel de acceso del procedimiento más que la propiedad, intente trasladar la instrucción que lee el valor de la propiedad a una región de código que tenga un mejor acceso a la propiedad.

## <a name="see-also"></a>Vea también

- [Procedimientos de propiedad](../../programming-guide/language-features/procedures/property-procedures.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
