---
title: Procedimiento Ordenar una matriz en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3f4dbd6dce0957de3451b1f29c3a67ccd6791045
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838084"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Procedimiento Ordenar una matriz en Visual Basic
En este ejemplo declara una matriz de `String` objetos denominados `zooAnimals`, lo rellena y, a continuación, ordena alfabéticamente.  
  
## <a name="example"></a>Ejemplo  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Acceso a Mscorlib.dll y <xref:System> espacio de nombres.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   Matriz está vacía (<xref:System.ArgumentNullException> clase)  
  
-   La matriz es multidimensional (<xref:System.RankException> clase)  
  
-   Uno o más elementos de la matriz no implementan la <xref:System.IComparable> interfaz (<xref:System.InvalidOperationException> clase)  
  
## <a name="see-also"></a>Vea también

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Colecciones](../../concepts/collections.md)
- [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
