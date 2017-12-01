---
title: '&#39; Conjunto de &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords: BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Conjunto de &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible
Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso a la propiedad `Set` procedimiento.  
  
 Si el [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md) está marcada con un acceso más restrictivo nivel que su [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md), se producirá un error en un intento para establecer el valor de propiedad en los casos siguientes:  
  
-   El `Set` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código que realiza la llamada está fuera de la clase o estructura en la que se define la propiedad.  
  
-   El `Set` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.  
  
-   El `Set` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.  
  
 **Id. de error:** BC31102  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si tiene control sobre el código de origen define la propiedad, considere la posibilidad de declarar el `Set` procedimiento con el mismo nivel de acceso que la propiedad en Sí.  
  
-   Si no tiene control sobre el código de origen define la propiedad, o si debe restringir el `Set` procedimiento nivel de acceso a la propiedad en Sí, intente mover la instrucción que establece el valor de propiedad a una región de código que tiene un mejor acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
