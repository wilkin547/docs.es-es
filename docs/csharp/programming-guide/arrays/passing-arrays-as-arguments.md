---
title: 'Pasar matrices como argumentos: Guía de programación de C#'
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705696"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Pasar matrices como argumentos (Guía de programación de C#)

Las matrices se pueden pasar como argumentos a parámetros de método. Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.

## <a name="passing-single-dimensional-arrays-as-arguments"></a>Pasar matrices unidimensionales como argumentos

Puede pasar una matriz unidimensional inicializada a un método. Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

En el siguiente código, se muestra una implementación parcial del método de impresión.

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a>Ejemplo

En el ejemplo siguiente, una matriz de cadenas se inicializa y pasa como un argumento a un método `DisplayArray` para cadenas. El método muestra los elementos de la matriz. A continuación, el método `ChangeArray` invierte los elementos de la matriz y, después, el método `ChangeArrayElements` modifica los tres primeros elementos de la matriz. Después de cada devolución de método, el método `DisplayArray` muestra que pasar una matriz por valor no impide que se cambien los elementos de la matriz.

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a>Pasar matrices multidimensionales como argumentos

Pase una matriz multidimensional inicializada a un método de la misma manera que pasa una matriz unidimensional.

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

En el código siguiente, se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como su argumento.

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

Puede inicializar y pasar una matriz nueva en un solo paso, como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a>Ejemplo

En el ejemplo siguiente, una matriz bidimensional de enteros se inicializa y pasa al método `Print2DArray`. El método muestra los elementos de la matriz.

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Matrices](index.md)
- [Matrices unidimensionales](single-dimensional-arrays.md)
- [Matrices multidimensionales](multidimensional-arrays.md)
- [Matrices escalonadas](jagged-arrays.md)
