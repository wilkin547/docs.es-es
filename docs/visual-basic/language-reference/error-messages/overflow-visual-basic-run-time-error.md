---
title: "Desbordamiento (Error en tiempo de ejecuci&#243;n de Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrERRID_Overflow"
dev_langs: 
  - "VB"
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Desbordamiento (Error en tiempo de ejecuci&#243;n de Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se produce un desbordamiento cuando intenta una asignación que supera los límites del destino de la asignación.  
  
### Para corregir este error  
  
1.  Asegúrese de que los resultados de asignaciones, cálculos y conversiones de tipos de datos no son demasiado largos para estar representados dentro del intervalo de variables permitido para ese tipo de valor y asigne el valor a una variable de un tipo que pueda contener un intervalo más amplio de valores, si es necesario.  
  
2.  Asegúrese de que las asignaciones de propiedades se ajustan al intervalo de la propiedad para la que se han creado.  
  
3.  Asegúrese de que los números utilizados en cálculos que se convierten a enteros no tienen resultados más largos que los enteros.  
  
## Vea también  
 <xref:System.Int32.MaxValue?displayProperty=fullName>   
 <xref:System.Double.MaxValue?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)