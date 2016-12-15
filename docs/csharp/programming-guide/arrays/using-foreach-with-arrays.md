---
title: "Utilizar foreach con matrices (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], foreach"
  - "foreach (instrucción) [C#], usar con matrices"
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar foreach con matrices (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# también proporciona la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  Esta instrucción ofrece una manera sencilla y limpia de recorrer en iteración los elementos de una matriz o cualquier colección enumerable.  La instrucción `foreach` procesa los elementos en el orden devuelto por el enumerador del tipo de colección o matriz, normalmente del elemento 0 al último.  Por ejemplo, el siguiente código crea una matriz denominada `numbers` y la recorre en iteración mediante la instrucción `foreach`:  
  
 [!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Con las matrices multidimensionales, se puede usar el mismo método para recorrer en iteración los elementos, por ejemplo:  
  
 [!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 Sin embargo, con las matrices multidimensionales, usar un bucle [for](../../../csharp/language-reference/keywords/for.md) anidado ofrece un mayor control sobre los elementos de la matriz.  
  
## Vea también  
 <xref:System.Array>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)