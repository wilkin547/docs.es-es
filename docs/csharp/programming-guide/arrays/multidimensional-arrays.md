---
title: "Matrices multidimensionales (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
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
ms.openlocfilehash: 0203046e2038e97cf791141f6863fd8940b22ea4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="multidimensional-arrays-c-programming-guide"></a>Matrices multidimensionales (Guía de programación de C#)
Las matrices pueden tener varias dimensiones. Por ejemplo, la siguiente declaración crea una matriz bidimensional de cuatro filas y dos columnas.  
  
 [!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 La siguiente declaración crea una matriz de tres dimensiones, 4, 2 y 3.  
  
 [!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Inicialización de matriz  
 La matriz se puede inicializar en la declaración como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 También se puede inicializar la matriz sin especificar el intervalo.  
  
 [!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Si opta por declarar una variable de matriz sin inicializarla, deberá usar el operador `new` para asignar una matriz a la variable. El uso de `new` se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 En el ejemplo siguiente se asigna un valor a un elemento de matriz determinado.  
  
 [!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 De igual forma, en el ejemplo siguiente se obtiene el valor de un elemento de matriz determinado y se asigna a la variable `elementValue`.  
  
 [!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 El ejemplo de código siguiente inicializa los elementos de matriz con valores predeterminados (salvo las matrices escalonadas).  
  
 [!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)

