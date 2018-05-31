---
title: Utilizar foreach con matrices (Guía de programación de C#)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: b858f35167e24390a729769487ce98908a3d349f
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549460"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Utilizar foreach con matrices (Guía de programación de C#)

La instrucción [foreach](../../language-reference/keywords/foreach-in.md) ofrece una manera sencilla y limpia de iterar los elementos de una matriz.

Para matrices unidimensionales, la instrucción `foreach` procesa los elementos en orden creciente de índice, comenzando con el índice 0 y terminando con el índice `Length - 1`:

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

En el caso de matrices multidimensionales, los elementos se recorren de tal manera que primero se incrementan los índices de la dimensión más a la derecha, luego la siguiente dimensión a la izquierda, y así sucesivamente a la izquierda:

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

En cambio, con las matrices multidimensionales, usar un bucle [for](../../language-reference/keywords/for.md) anidado ofrece un mayor control sobre el orden en el que se procesan los elementos de la matriz.

## <a name="see-also"></a>Vea también  
 <xref:System.Array>  
 [Guía de programación de C#](../index.md)  
 [Matrices](index.md)  
 [Matrices unidimensionales](single-dimensional-arrays.md)  
 [Matrices multidimensionales](multidimensional-arrays.md)  
 [Matrices escalonadas](jagged-arrays.md)
