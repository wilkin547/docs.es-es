---
title: "&lt;tipo1&gt;&#39;&lt;nombreDeTipo&gt;&#39; debe implementar &#39;&lt;nombreDeM&#233;todo&gt;&#39; para la interfaz &#39;&lt;nombreDeInterfaz&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30149"
  - "bc30149"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30149"
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &lt;tipo1&gt;&#39;&lt;nombreDeTipo&gt;&#39; debe implementar &#39;&lt;nombreDeM&#233;todo&gt;&#39; para la interfaz &#39;&lt;nombreDeInterfaz&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz.  Deben implementarse todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30149  
  
### Para corregir este error  
  
1.  Declare un procedimiento con el mismo nombre y firma que los definidos en la interfaz.  Asegúrese de incluir al menos la instrucción `End Function` o `End Sub`.  
  
2.  Agregue una cláusula `Implements` al final de las instrucciones `Function` o `Sub`.  Por ejemplo:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## Vea también  
 [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)