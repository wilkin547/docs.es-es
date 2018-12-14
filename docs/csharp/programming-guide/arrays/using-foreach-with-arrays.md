---
title: Uso de foreach con matrices (Guía de programación de C#)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 217408600e40d2ce5197f207c007b858ff3145d7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147049"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Uso de foreach con matrices (Guía de programación de C#)

La instrucción [foreach](../../language-reference/keywords/foreach-in.md) ofrece una manera sencilla y limpia de iterar los elementos de una matriz.

Para matrices unidimensionales, la instrucción `foreach` procesa los elementos en orden creciente de índice, comenzando con el índice 0 y terminando con el índice `Length - 1`:

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

En el caso de matrices multidimensionales, los elementos se recorren de tal manera que primero se incrementan los índices de la dimensión más a la derecha, luego la siguiente dimensión a la izquierda, y así sucesivamente a la izquierda:

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

En cambio, con las matrices multidimensionales, usar un bucle [for](../../language-reference/keywords/for.md) anidado ofrece un mayor control sobre el orden en el que se procesan los elementos de la matriz.

## <a name="see-also"></a>Vea también

- <xref:System.Array>  
- [Guía de programación de C#](../index.md)  
- [Matrices](index.md)  
- [Matrices unidimensionales](single-dimensional-arrays.md)  
- [Matrices multidimensionales](multidimensional-arrays.md)  
- [Matrices escalonadas](jagged-arrays.md)
