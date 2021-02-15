---
description: 'Más información acerca de cómo: ordenar una matriz en Visual Basic'
title: Procedimiento para ordenar una matriz
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: ea030b63dbbb5f5ea1d6160757afe2e9b58f7c21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462768"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Cómo: ordenar una matriz en Visual Basic

En este artículo se muestra un ejemplo de cómo ordenar una matriz de cadenas en Visual Basic.

## <a name="example"></a>Ejemplo

En este ejemplo se declara una matriz de `String` objetos denominada `zooAnimals` , se rellena y, a continuación, se ordena alfabéticamente:
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a>Programación sólida

Las condiciones siguientes pueden provocar una excepción:

- La matriz está vacía ( <xref:System.ArgumentNullException> clase).
- La matriz es multidimensional ( <xref:System.RankException> clase).
- Uno o varios elementos de la matriz no implementan la <xref:System.IComparable> interfaz ( <xref:System.InvalidOperationException> clase).

## <a name="see-also"></a>Vea también

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Matrices](index.md)
- [Solución de problemas de matrices](troubleshooting-arrays.md)
- [Colecciones](../../concepts/collections.md)
- [Instrucción For Each...Next](../../../language-reference/statements/for-each-next-statement.md)
