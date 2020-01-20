---
title: 'Matrices unidimensionales: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 07c6061bfc66b1640d0eacca217302feff1a390a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715030"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrices unidimensionales (Guía de programación de C#)

Puede declarar una matriz unidimensional de cinco enteros tal y como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 Esta matriz contiene los elementos de `array[0]` a `array[4]`. El operador [new](../../language-reference/operators/new-operator.md) se usa para crear la matriz e inicializar los elementos de matriz con sus valores predeterminados. En este ejemplo, todos los elementos de matriz se inicializan en cero.  
  
 Una matriz que almacena elementos de cadena se puede declarar de la misma forma. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a>Inicialización de matriz

 Es posible inicializar una matriz en la declaración, en cuyo caso, el especificador de longitud no es necesario porque ya lo proporciona el número de elementos de la lista de inicialización. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 Se puede inicializar una matriz de cadenas del mismo modo. La siguiente es una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante un nombre de un día:  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 Al inicializar una matriz en la declaración, puede usar los siguientes métodos abreviados:  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 Es posible declarar una variable de matriz sin inicializarla, pero debe usar el operador `new` al asignar una matriz a esta variable. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 C# 3.0 presenta matrices con tipo implícito. Para obtener más información, vea [Matrices con asignación implícita de tipos](./implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Matrices de tipo de valor y tipo de referencia

 Tenga en cuenta la siguiente declaración de matriz:  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia. Si es un tipo de valor, la instrucción crea una matriz de 10 elementos y cada uno de ellos tiene el tipo `SomeType`. Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.  
  
Para obtener más información sobre los tipos de valor y de referencia, consulte [Tipos de valor ](../../language-reference/keywords/value-types.md) y [Tipos de referencia](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Guía de programación de C#](../index.md)
- [Matrices](./index.md)
- [Matrices multidimensionales](./multidimensional-arrays.md)
- [Matrices escalonadas](./jagged-arrays.md)
