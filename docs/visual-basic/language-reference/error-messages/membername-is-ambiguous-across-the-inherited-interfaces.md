---
title: "&#39;&lt;nombreDeMiembro&gt;&#39; es ambiguo en las interfaces heredadas &#39;&lt;nombreDeInterfaz1&gt;&#39; y &#39;&lt;nombreDeInterfaz2&gt;&#39; | Microsoft Docs"
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
  - "vbc30685"
  - "bc30685"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30685"
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombreDeMiembro&gt;&#39; es ambiguo en las interfaces heredadas &#39;&lt;nombreDeInterfaz1&gt;&#39; y &#39;&lt;nombreDeInterfaz2&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La interfaz hereda dos o más miembros con el mismo nombre de diferentes interfaces.  
  
 **Identificador de error:** BC30685  
  
### Para corregir este error  
  
-   Convierta el tipo del valor al de la interfaz base que desea usar; por ejemplo:  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)