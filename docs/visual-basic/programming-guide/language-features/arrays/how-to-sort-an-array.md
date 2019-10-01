---
title: Procedimiento Ordenar una matriz en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700976"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Cómo: ordenar una matriz en Visual Basic

En este artículo se muestra un ejemplo de cómo ordenar una matriz de cadenas en Visual Basic.

## <a name="example"></a>Ejemplo

En este ejemplo se declara una matriz de objetos `String` denominada `zooAnimals`, se rellena y, a continuación, se ordena alfabéticamente:
  
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

- La matriz está vacía (clase <xref:System.ArgumentNullException>).
- La matriz es multidimensional (clase <xref:System.RankException>).
- Uno o varios elementos de la matriz no implementan la interfaz <xref:System.IComparable> (clase <xref:System.InvalidOperationException>).

## <a name="see-also"></a>Vea también

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Matrices](index.md)
- [Solución de problemas de matrices](troubleshooting-arrays.md)
- [Colecciones](../../concepts/collections.md)
- [For Each...Next (instrucción)](../../../language-reference/statements/for-each-next-statement.md)
