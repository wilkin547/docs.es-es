---
title: "El nombre de una variable de rango s&#243;lo se puede inferir a partir de un nombre simple o completo sin argumentos | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36599"
  - "bc36599"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36599"
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# El nombre de una variable de rango s&#243;lo se puede inferir a partir de un nombre simple o completo sin argumentos
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un elemento de programación que toma uno o más argumentos está incluido en una consulta LINQ.  El compilador no puede deducir una variable de rango de ese elemento de programación.  
  
 **Id. de error:** BC36599  
  
### Para corregir este error  
  
1.  Proporcione un nombre de variable explícito para el elemento de programación, como se muestra en el código siguiente:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias = SampleFunction(var1), var1  
```  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)