---
title: "El n&#250;mero de &#237;ndices sobrepasa el n&#250;mero de dimensiones de la matriz indizada | Microsoft Docs"
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
  - "bc30106"
  - "vbc30106"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30106"
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El n&#250;mero de &#237;ndices sobrepasa el n&#250;mero de dimensiones de la matriz indizada
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El número de índices usado para obtener acceso a un elemento de matriz debe ser exactamente igual al rango de la matriz, es decir, el número de dimensiones que tiene declaradas.  
  
 **Identificador de error:** BC30106  
  
### Para corregir este error  
  
-   Quite subíndices de la referencia de la matriz hasta que el número total de subíndices sea igual a su rango.  Por ejemplo:  
  
    ```  
    [Visual Basic]  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)