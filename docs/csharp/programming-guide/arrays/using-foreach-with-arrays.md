---
title: "Utilizar foreach con matrices (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 797cb9a63a5e1009b170b2afda8634bd21a50035
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Utilizar foreach con matrices (Guía de programación de C#)
C# también proporciona la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Esta instrucción ofrece una manera sencilla y limpia de recorrer en iteración los elementos de una matriz o cualquier colección enumerable. La instrucción `foreach` procesa los elementos en el orden devuelto por el enumerador del tipo de colección o matriz, normalmente del elemento 0 al último. Por ejemplo, el siguiente código crea una matriz denominada `numbers` y la recorre en iteración mediante la instrucción `foreach`:  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Con las matrices multidimensionales, se puede usar el mismo método para recorrer en iteración los elementos, por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 En cambio, con las matrices multidimensionales, usar un bucle [for](../../../csharp/language-reference/keywords/for.md) anidado ofrece un mayor control sobre los elementos de la matriz.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)
