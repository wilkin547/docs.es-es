---
title: 'Matrices escalonadas: Guía de programación de C#'
description: Una matriz escalonada de C# es una matriz cuyos elementos son matrices de diferentes tamaños. Aprenda a declarar y inicializar matrices escalonadas, así como a acceder a ellas.
ms.date: 12/18/2020
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 6d4fb939fb6594c7644a80eb688ea852ddf8a5c5
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737286"
---
# <a name="jagged-arrays-c-programming-guide"></a>Matrices escalonadas (Guía de programación de C#)

Una matriz escalonada es una matriz cuyos elementos son matrices, posiblemente de diferentes tamaños. Una matriz escalonada se denomina a veces "matriz de matrices". En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.

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

 Es posible mezclar matrices multidimensionales y escalonadas. La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes. Para obtener más información, vea [Matrices multidimensionales](./multidimensional-arrays.md).

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
