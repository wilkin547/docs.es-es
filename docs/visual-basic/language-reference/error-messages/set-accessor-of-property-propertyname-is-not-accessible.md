---
title: El descriptor de acceso 'Set' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 1539eb1652d93402c349c65f77a3edc65b3beb57
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277568"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a>'Set' descriptor de acceso de propiedad '\<propertyname >' no es accesible
Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso a la propiedad `Set` procedimiento.  
  
 Si el [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md) está marcada con un acceso más restrictivo nivel que su [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), podría producirse un error de un intento para establecer el valor de propiedad en los casos siguientes:  
  
-   El `Set` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.  
  
-   El `Set` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.  
  
-   El `Set` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.  
  
 **Identificador de error:** BC31102  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si tiene el control del código fuente definiendo la propiedad, considere la posibilidad de declarar la `Set` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.  
  
-   Si no tiene control sobre el código fuente definiendo la propiedad, o si debe restringir el `Set` procedimiento de nivel de acceso a la propiedad propiamente dicha, intente mover la instrucción que establece el valor de propiedad en una región de código que tiene un mejor acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
