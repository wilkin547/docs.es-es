---
title: "Esta matriz es fija o est&#225; bloqueada temporalmente (Visual Basic) | Microsoft Docs"
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
  - "vbrID10"
dev_langs: 
  - "VB"
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Esta matriz es fija o est&#225; bloqueada temporalmente (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este error tiene las causas posibles siguientes:  
  
-   Uso de `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.  
  
-   Redimensionamiento de una matriz dinámica de nivel de módulo, donde se ha pasado un elemento como argumento a un procedimiento.  Si se ha pasado un elemento, se ha bloqueado la matriz para impedir la desasignación de memoria para el parámetro de referencia dentro del procedimiento.  
  
-   Intento de asignar un valor a una variable `Variant` que contiene una matriz, pero la variable `Variant` está bloqueada actualmente.  
  
### Para corregir este error  
  
1.  Haga dinámica la matriz original en lugar de fija declarándola con `ReDim` \(si se ha declarado la matriz dentro del procedimiento\) o declarándola sin especificar el número de elementos \(si se ha declarado la matriz en el nivel de módulo\).  
  
2.  Determine si realmente necesita pasar el elemento, dado que es visible dentro de todos los procedimientos del módulo.  
  
3.  Determine la causa del bloqueo del `Variant` y soluciónelo.  
  
## Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)