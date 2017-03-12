---
title: "El descriptor de acceso &#39;Set&#39; de la propiedad &#39;&lt;nombre de propiedad&gt;&#39; no est&#225; accesible | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31102"
  - "bc31102"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31102"
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# El descriptor de acceso &#39;Set&#39; de la propiedad &#39;&lt;nombre de propiedad&gt;&#39; no est&#225; accesible
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso al procedimiento `Set` de la propiedad.  
  
 Si la [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md) está marcada con un nivel de acceso más restrictivo que su [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md), el intento de establecer el valor de propiedad podría producir un error en los siguientes casos:  
  
-   La instrucción `Set` está marcada como [Private](../../../visual-basic/language-reference/modifiers/private.md) y el código de llamada está fuera de la clase o estructura en que está definida la propiedad.  
  
-   La instrucción `Set` está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en que está definida la propiedad, ni en una clase derivada.  
  
-   La instrucción `Set` se marca como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que está definida la propiedad.  
  
 **Identificador de error:** BC31102  
  
### Para corregir este error  
  
-   Si tiene control sobre el código fuente que define la propiedad, plantéese declarar el procedimiento `Set` con el mismo nivel de acceso que la propiedad en sí.  
  
-   Si no tiene control sobre el código fuente que define la propiedad, o si debe restringir el nivel de acceso al procedimiento `Set` en lugar de a la propiedad en sí, intente mover la instrucción que establece el valor de propiedad a una región de código que tenga mejor acceso a la propiedad.  
  
## Vea también  
 [Procedimientos de propiedad](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)