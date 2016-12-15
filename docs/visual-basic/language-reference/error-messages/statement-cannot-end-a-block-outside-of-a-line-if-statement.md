---
title: "La instrucci&#243;n no puede terminar un bloque fuera de una l&#237;nea de la instrucci&#243;n &#39;If&#39; | Microsoft Docs"
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
  - "vbc32005"
  - "bc32005"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32005"
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La instrucci&#243;n no puede terminar un bloque fuera de una l&#237;nea de la instrucci&#243;n &#39;If&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una instrucción `If` de una sola línea contiene varias instrucciones separadas por signos de dos puntos \(:\), una de las cuales es una instrucción `End` para un bloque de control externo a la instrucción `If`.  Las instrucciones `If` de una sola línea no utilizan la instrucción `End If`.  
  
 **Identificador de error:** BC32005  
  
### Para corregir este error  
  
-   Desplace la instrucción `If` de una sola línea fuera del bloque de control que contiene la instrucción `End If`.  
  
## Vea también  
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)