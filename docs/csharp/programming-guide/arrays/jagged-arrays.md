---
title: 'Matrices escalonadas: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 56013f0143d5efcb31a476909cb6e92504ff0dbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705709"
---
# <a name="jagged-arrays-c-programming-guide"></a>Matrices escalonadas (Guía de programación de C#)

Una matriz escalonada es una matriz cuyos elementos son matrices. Los elementos de una matriz escalonada pueden ser de diferentes dimensiones y tamaños. Una matriz escalonada se denomina a veces "matriz de matrices". En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.  
  
 La siguiente es una declaración de una matriz unidimensional que tiene tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 Para poder usar `jaggedArray`, se deben inicializar sus elementos. Puede inicializar los elementos de esta forma:  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 Cada uno de los elementos es una matriz unidimensional de enteros. El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.  
  
 También es posible usar inicializadores para rellenar los elementos de matriz con valores, en cuyo caso no es necesario el tamaño de la matriz. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 También puede inicializar la matriz en la declaración de esta forma:  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 Puede usar la siguiente forma abreviada. Tenga en cuenta que no puede omitir el operador `new` de la inicialización de elementos porque no hay ninguna inicialización predeterminada para los elementos:  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.  
  
 Puede tener acceso a elementos individuales de la matriz como en estos ejemplos:  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 Es posible mezclar matrices multidimensionales y escalonadas. La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes. Para obtener más información sobre las matrices bidimensionales, vea [Matrices multidimensionales](./multidimensional-arrays.md).  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 Puede tener acceso a los elementos individuales como se muestra en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz (valor `5`):  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 El método `Length` devuelve el número de matrices contenidos en la matriz escalonada. Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 devuelve un valor de 3.  
  
## <a name="example"></a>Ejemplo

 En este ejemplo, se crea una matriz cuyos elementos son matrices. Cada uno de los elementos de matriz tiene un tamaño diferente.  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Guía de programación de C#](../index.md)
- [Matrices](./index.md)
- [Matrices unidimensionales](./single-dimensional-arrays.md)
- [Matrices multidimensionales](./multidimensional-arrays.md)
