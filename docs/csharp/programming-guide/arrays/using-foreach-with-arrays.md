---
title: "Utilizar foreach con matrices (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a1d0b704233b110b5f499b8186a4a901f9b5408f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Utilizar foreach con matrices (Guía de programación de C#)
C# también proporciona la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Esta instrucción ofrece una manera sencilla y limpia de recorrer en iteración los elementos de una matriz o cualquier colección enumerable. La instrucción `foreach` procesa los elementos en el orden devuelto por el enumerador del tipo de colección o matriz, normalmente del elemento 0 al último. Por ejemplo, el siguiente código crea una matriz denominada `numbers` y la recorre en iteración mediante la instrucción `foreach`:  
  
 [!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Con las matrices multidimensionales, se puede usar el mismo método para recorrer en iteración los elementos, por ejemplo:  
  
 [!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 En cambio, con las matrices multidimensionales, usar un bucle [for](../../../csharp/language-reference/keywords/for.md) anidado ofrece un mayor control sobre los elementos de la matriz.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)

