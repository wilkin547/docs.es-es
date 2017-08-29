---
title: "Matrices escalonadas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
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
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a>Matrices escalonadas (Guía de programación de C#)
Una matriz escalonada es una matriz cuyos elementos son matrices. Los elementos de una matriz escalonada pueden ser de diferentes dimensiones y tamaños. Una matriz escalonada se denomina a veces "matriz de matrices". En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.  
  
 La siguiente es una declaración de una matriz unidimensional que tiene tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Para poder usar `jaggedArray`, se deben inicializar sus elementos. Puede inicializar los elementos de esta forma:  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Cada uno de los elementos es una matriz unidimensional de enteros. El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.  
  
 También es posible usar inicializadores para rellenar los elementos de matriz con valores, en cuyo caso no es necesario el tamaño de la matriz. Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 También puede inicializar la matriz en la declaración de esta forma:  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 Puede usar la siguiente forma abreviada. Tenga en cuenta que no puede omitir el operador `new` de la inicialización de elementos porque no hay ninguna inicialización predeterminada para los elementos:  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.  
  
 Puede tener acceso a elementos individuales de la matriz como en estos ejemplos:  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 Es posible mezclar matrices multidimensionales y escalonadas. La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes. Para obtener más información sobre las matrices bidimensionales, vea [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 Puede tener acceso a los elementos individuales como se muestra en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz (valor `5`):  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 El método `Length` devuelve el número de matrices contenidos en la matriz escalonada. Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 devuelve un valor de 3.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se crea una matriz cuyos elementos son matrices. Cada uno de los elementos de matriz tiene un tamaño diferente.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

