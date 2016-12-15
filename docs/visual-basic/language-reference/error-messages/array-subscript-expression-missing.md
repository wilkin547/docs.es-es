---
title: "Falta la expresi&#243;n de sub&#237;ndice de matriz | Microsoft Docs"
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
  - "bc30306"
  - "vbc30306"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30306"
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Falta la expresi&#243;n de sub&#237;ndice de matriz
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una inicialización de matriz omite uno o más de los subíndices que definen los límites de la matriz.  Por ejemplo, la instrucción podría contener la expresión `myArray (5,5,,10)` que omite el tercer subíndice.  
  
 **Identificador de error:** BC30306  
  
### Para corregir este error  
  
-   Suministre el subíndice que no ha incluido.  
  
## Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)