---
title: "La variable de rango &lt;variable&gt; oculta una variable en un bloque de inclusi&#243;n, una variable de rango definida anteriormente o una variable declarada de forma impl&#237;cita en una expresi&#243;n de consulta | Microsoft Docs"
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
  - "bc36633"
  - "vbc36633"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36633"
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La variable de rango &lt;variable&gt; oculta una variable en un bloque de inclusi&#243;n, una variable de rango definida anteriormente o una variable declarada de forma impl&#237;cita en una expresi&#243;n de consulta
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El nombre de una variable de rango especificado en una cláusula `Select`, `From`, `Aggregate` o `Let` duplica el nombre de una variable de rango definido anteriormente en la consulta o el nombre de una variable declarada de forma implícita por la consulta, como un nombre de campo o el nombre de una función de agregado.  
  
 **Id. de error:** BC36633  
  
### Para corregir este error  
  
-   Asegúrese de que todas las variables de rango de un ámbito determinado de la consulta tienen nombres únicos.  Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un único ámbito.  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Let \(Cláusula\)](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Aggregate \(Cláusula\)](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)