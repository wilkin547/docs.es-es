---
title: "Una matriz declarada como variable de control de bucle no se puede declarar con un tama&#241;o inicial | Microsoft Docs"
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
  - "vbc32039"
  - "bc32039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32039"
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Una matriz declarada como variable de control de bucle no se puede declarar con un tama&#241;o inicial
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un bucle `For Each` usa una matriz como su variable de iteración *elemento* pero inicializa esa matriz.  
  
 Las instrucciones siguientes muestran cómo se puede generar este error.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 La primera instrucción `For Each` es la manera correcta de tener acceso a los elementos de `arrayList`.  La segunda instrucción `For Each` genera este error.  
  
 **Identificador de error:** BC32039  
  
### Para corregir este error  
  
-   Quite la inicialización de la declaración de la variable de iteración *elemento*.  
  
## Vea también  
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)