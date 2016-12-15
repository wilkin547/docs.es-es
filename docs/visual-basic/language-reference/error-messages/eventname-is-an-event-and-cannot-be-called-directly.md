---
title: "&#39;&lt;nombreDeEvento&gt;&#39; es un evento y no se le puede llamar directamente | Microsoft Docs"
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
  - "bc32022"
  - "vbc32022"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32022"
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombreDeEvento&gt;&#39; es un evento y no se le puede llamar directamente
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<`eventname`\>' es un evento, por lo que no se puede invocarlo directamente.  Utilice una instrucción `RaiseEvent` para provocar un evento.  
  
 La llamada a un procedimiento especifica un evento para el nombre del procedimiento.  Un controlador de evento es un procedimiento, pero el evento es un dispositivo de señalización, que debe generarse y controlarse.  
  
 **Identificador de error:** BC32022  
  
### Para corregir este error  
  
1.  Use una instrucción `RaiseEvent` para señalizar un evento e invocar el procedimiento o procedimientos que lo controlan.  
  
## Vea también  
 [RaiseEvent \(Instrucción\)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)