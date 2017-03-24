---
title: "&#39;#ElseIf&#39; debe ir precedida de la instrucci&#243;n &#39;#If&#39; o &#39;#ElseIf&#39; correspondiente | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30014"
  - "bc30014"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30014"
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;#ElseIf&#39; debe ir precedida de la instrucci&#243;n &#39;#If&#39; o &#39;#ElseIf&#39; correspondiente
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`#ElseIf` es una directiva de compilación condicional.  Una cláusula `#ElseIf` debe ir precedida de una cláusula `#If` o `#ElseIf` correspondiente.  
  
 **Identificador de error:** BC30014  
  
### Para corregir este error  
  
1.  Compruebe que la cláusula `#If`  o `#ElseIf` anterior no está separada de está cláusula `#ElseIf` por un bloque de compilación condicional intermedio o una cláusula `#End If` incorrectamente colocada.  
  
2.  Si `#ElseIf` va precedida de una directiva `#Else`, quite `#Else` o cámbiela a `#ElseIf`.  
  
3.  Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.  
  
## Vea también  
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)