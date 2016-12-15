---
title: "El descriptor de acceso &#39;Get&#39; de la propiedad &#39;&lt;nombre de propiedad&gt;&#39; no est&#225; accesible | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31103"
  - "bc31103"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31103"
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El descriptor de acceso &#39;Get&#39; de la propiedad &#39;&lt;nombre de propiedad&gt;&#39; no est&#225; accesible
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso al procedimiento `Get` de la propiedad.  
  
 Si la [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md) está marcada con un nivel de acceso más restrictivo que su [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md), el intento de leer el valor de propiedad podría producir un error en los siguientes casos:  
  
-   La instrucción `Get` está marcada como [Private](../../../visual-basic/language-reference/modifiers/private.md) y el código de llamada está fuera de la clase o estructura en que está definida la propiedad.  
  
-   La instrucción `Get` está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en que está definida la propiedad, ni en una clase derivada.  
  
-   La instrucción `Get` se marca como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que está definida la propiedad.  
  
 **Identificador de error:** BC31103  
  
### Para corregir este error  
  
-   Si tiene control sobre el código fuente que define la propiedad, plantéese declarar el procedimiento `Get` con el mismo nivel de acceso que la propiedad en sí.  
  
-   Si no tiene control sobre el código fuente que define la propiedad, o si debe restringir el nivel de acceso al procedimiento `Get` en lugar de a la propiedad en sí, intente mover la instrucción que lee el valor de propiedad a una región de código que tenga mejor acceso a la propiedad.  
  
## Vea también  
 [Procedimientos de propiedad](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)