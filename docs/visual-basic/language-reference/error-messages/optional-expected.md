---
title: "Se esperaba &#39;Optional&#39; | Microsoft Docs"
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
  - "bc30202"
  - "vbc30202"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30202"
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Se esperaba &#39;Optional&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un argumento opcional de una declaración de procedimiento viene seguido de un argumento requerido.  Cada argumento que sigue a un argumento opcional también debe ser opcional.  
  
 **Identificador de error:** BC30202  
  
### Para corregir este error  
  
1.  Si se deseaba que el argumento fuera requerido, muévalo para que preceda al primer argumento original de la lista de argumentos.  
  
2.  Si debía ser opcional, use la palabra clave `Optional`.  
  
## Vea también  
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)