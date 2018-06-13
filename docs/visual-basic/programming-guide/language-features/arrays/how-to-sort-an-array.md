---
title: 'Cómo: Ordenar una matriz en Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: a067c40e1dd0e881516cbc7769cb9afb879d1b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646320"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Cómo: Ordenar una matriz en Visual Basic
Este ejemplo declara una matriz de `String` objetos denominados `zooAnimals`lo rellena y, a continuación, ordena alfabéticamente.  
  
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
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Colecciones](../../concepts/collections.md)  
 [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
