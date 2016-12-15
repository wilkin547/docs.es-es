---
title: "Los l&#237;mites de matriz no pueden aparecer en los especificadores de tipo | Microsoft Docs"
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
  - "vbc30638"
  - "bc30638"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30638"
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Los l&#237;mites de matriz no pueden aparecer en los especificadores de tipo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los tamaños de matriz no se pueden declarar como parte de un especificador de tipo de datos.  
  
 **Identificador de error:** BC30638  
  
### Para corregir este error  
  
-   Especifique el tamaño de la matriz inmediatamente después del nombre de la variable en lugar de hacerlo tras el tipo, como se muestra en el siguiente ejemplo:  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Defina una matriz e inicialícela con el número de elementos que desee, como se muestra en el siguiente ejemplo:  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)