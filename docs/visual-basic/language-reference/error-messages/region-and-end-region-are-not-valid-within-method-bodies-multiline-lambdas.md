---
title: "Las instrucciones &#39;#Region&#39; y &#39;#End Region&#39; no son v&#225;lidas en los cuerpos de m&#233;todo y operaciones lambda de varias l&#237;neas | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32025"
  - "vbc32025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32025"
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Las instrucciones &#39;#Region&#39; y &#39;#End Region&#39; no son v&#225;lidas en los cuerpos de m&#233;todo y operaciones lambda de varias l&#237;neas
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El bloque `#Region` debe declararse en el nivel de clase, módulo o espacio de nombres.  Una región que se puede expandir o contraer puede incluir uno o varios procedimientos, pero no puede empezar o terminar dentro de un procedimiento.  
  
 **Identificador de error:** BC32025  
  
### Para corregir este error  
  
1.  Asegúrese de que el procedimiento precedente se termine correctamente con una instrucción `End Function` o `End Sub`.  
  
2.  Asegúrese de que las directivas `#Region` y `#End Region` están en el mismo bloque de código.  
  
## Vea también  
 [\#Region \(Directiva\)](../../../visual-basic/language-reference/directives/region-directive.md)