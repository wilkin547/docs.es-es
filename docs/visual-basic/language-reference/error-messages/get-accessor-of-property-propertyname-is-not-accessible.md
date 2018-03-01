---
title: '&#39; Get &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 167e040570af1fc78ce48f5e930e54981ba909ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Get &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible
Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso a la propiedad `Get` procedimiento.  
  
 Si el [instrucción Get](../../../visual-basic/language-reference/statements/get-statement.md) está marcada con un acceso más restrictivo nivel que su [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md), se producirá un error en un intento de leer el valor de propiedad en los casos siguientes:  
  
-   El `Get` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código que realiza la llamada está fuera de la clase o estructura en la que se define la propiedad.  
  
-   El `Get` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.  
  
-   El `Get` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.  
  
 **Id. de error:** BC31103  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si tiene control sobre el código de origen define la propiedad, considere la posibilidad de declarar el `Get` procedimiento con el mismo nivel de acceso que la propiedad en Sí.  
  
-   Si no tiene control sobre el código de origen define la propiedad, o si debe restringir el `Get` procedimiento nivel de acceso a la propiedad en Sí, intente mover la instrucción que lee el valor de propiedad a una región de código que tiene un mejor acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
