---
title: "La instrucci&#243;n &#39;Class&#39; debe terminar con la instrucci&#243;n &#39;End Class&#39; correspondiente | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30481"
  - "bc30481"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30481"
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# La instrucci&#243;n &#39;Class&#39; debe terminar con la instrucci&#243;n &#39;End Class&#39; correspondiente
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Class` se utiliza para comenzar un bloque `Class`; por tanto, sólo puede aparecer al principio del bloque y debe haber una instrucción `End Class` correspondiente para terminar el bloque.  O bien hay una instrucción `Class` redundante o bien no ha terminado el bloque `Class` con `End Class`.  
  
 **Identificador de error:** BC30481  
  
### Para corregir este error  
  
-   Busque la instrucción `Class` innecesaria y quítela.  
  
-   Termine el bloque `Class` con la instrucción `End Class` correspondiente.  
  
## Vea también  
 [End \<palabra clave\> \(Instrucción\)](../../../visual-basic/language-reference/statements/end-keyword-statement.md)   
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)