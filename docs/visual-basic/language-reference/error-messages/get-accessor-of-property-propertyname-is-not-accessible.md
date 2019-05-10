---
title: El descriptor de acceso 'Get' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 92cc6d732b59617a6043bd71a9549649ff1ad356
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662055"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a>'Get' descriptor de acceso de propiedad '\<propertyname >' no es accesible
Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso a la propiedad `Get` procedimiento.  
  
 Si el [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) está marcada con un acceso más restrictivo nivel que su [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), podría producirse un error de un intento de leer el valor de propiedad en los casos siguientes:  
  
- El `Get` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.  
  
- El `Get` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.  
  
- El `Get` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.  
  
 **Identificador de error:** BC31103  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si tiene el control del código fuente definiendo la propiedad, considere la posibilidad de declarar la `Get` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.  
  
- Si no tiene control sobre el código fuente definiendo la propiedad, o si debe restringir el `Get` procedimiento de nivel de acceso a la propiedad propiamente dicha, intente mover la instrucción que lee el valor de propiedad en una región de código que tiene un mejor acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
