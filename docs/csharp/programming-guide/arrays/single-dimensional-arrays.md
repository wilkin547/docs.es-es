---
title: "Matrices unidimensionales (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrices unidimensionales (Guía de programación de C#)
Puede declarar una matriz unidimensional de cinco enteros tal y como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Esta matriz contiene los elementos de `array[0]` a `array[4]`. El operador [new](../../../csharp/language-reference/keywords/new.md) se usa para crear la matriz e inicializar los elementos de matriz con sus valores predeterminados. En este ejemplo, todos los elementos de matriz se inicializan en cero.  
  
 Una matriz que almacena elementos de cadena se puede declarar de la misma forma. Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Inicialización de matriz  
 Es posible inicializar una matriz en la declaración, en cuyo caso, el especificador de rango no es necesario porque ya lo proporciona el número de elementos de la lista de inicialización. Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Se puede inicializar una matriz de cadenas del mismo modo. La siguiente es una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante un nombre de un día:  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Al inicializar una matriz en la declaración, puede usar los siguientes métodos abreviados:  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 Es posible declarar una variable de matriz sin inicializarla, pero debe usar el operador `new` al asignar una matriz a esta variable. Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 C# 3.0 presenta matrices con tipo implícito. Para obtener más información, vea [Matrices con asignación implícita de tipos](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Matrices de tipo de valor y tipo de referencia  
 Tenga en cuenta la siguiente declaración de matriz:  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia. Si es un tipo de valor, la instrucción crea una matriz de 10 elementos y cada uno de ellos tiene el tipo `SomeType`. Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.  
  
 Para obtener más información sobre los tipos de valor y de referencia, consulte [Types](../../../csharp/language-reference/keywords/types.md) (Tipos).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)

