---
title: "Las clases derivadas no pueden provocar eventos de clase base | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30029"
  - "bc30029"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30029"
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Las clases derivadas no pueden provocar eventos de clase base
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un evento sólo se puede provocar desde el espacio de nombres donde se declaró.  Por lo tanto, una clase no puede provocar eventos de ninguna otra clase, incluso una de la cual se derive.  
  
 **Identificador de error:** BC30029  
  
### Para corregir este error  
  
-   Mueva la instrucción `Event` o `RaiseEvent` para que pertenezcan a la misma clase.  
  
## Vea también  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent \(Instrucción\)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)