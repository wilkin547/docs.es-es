---
title: "Se esperaba una declaraci&#243;n | Microsoft Docs"
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
  - "vbc30188"
  - "bc30188"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30188"
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Se esperaba una declaraci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hay una instrucción no declarativa, como una instrucción de asignación o bucle, fuera de un procedimiento.  Sólo se permiten declaraciones fuera de los procedimientos.  
  
 Como alternativa, se declara un elemento de programación sin una palabra clave de declaración como `Dim` o `Const`.  
  
 **Identificador de error:** BC30188  
  
### Para corregir este error  
  
-   Mueva la instrucción no declarativa al cuerpo de un procedimiento.  
  
-   Comience la declaración con una palabra clave de declaración adecuada.  
  
-   Asegúrese de que la palabra clave de declaración no esté mal escrita.  
  
## Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)