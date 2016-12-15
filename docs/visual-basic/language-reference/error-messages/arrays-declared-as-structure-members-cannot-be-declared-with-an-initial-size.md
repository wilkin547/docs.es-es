---
title: "Las matrices declaradas como miembros de estructura no se pueden declarar con un tama&#241;o inicial | Microsoft Docs"
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
  - "vbc31043"
  - "bc31043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31043"
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Las matrices declaradas como miembros de estructura no se pueden declarar con un tama&#241;o inicial
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una matriz de una estructura está declarada con un tamaño inicial.  No puede inicializar ningún elemento de estructura y declarar un tamaño de matriz es una forma de inicialización.  
  
 **Identificador de error:** BC31043  
  
### Para corregir este error  
  
1.  Defina la matriz en la estructura como dinámico \(ningún tamaño inicial\).  
  
2.  Si necesita un tamaño de matriz determinado, puede cambiar las dimensiones de una matriz dinámica con [ReDim \(Instrucción\)](../../../visual-basic/language-reference/statements/redim-statement.md) cuando se está ejecutando su código.  Esto se ilustra en el siguiente ejemplo:  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Cómo: Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)