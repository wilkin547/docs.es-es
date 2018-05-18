---
title: Pasar matrices mediante Ref y Out (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: a186399125e01bb2535f3a8b488c6fbd85932246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a>Pasar matrices mediante Ref y Out (Guía de programación de C#)
Al igual que todos los parámetros [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), un parámetro `out` de un tipo de matriz debe asignarse antes de usarse; es decir, debe asignarlo el destinatario. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Al igual que todos los parámetros [ref](../../../csharp/language-reference/keywords/ref.md), un parámetro `ref` de un tipo de matriz debe asignarlo definitivamente el autor de la llamada. Por consiguiente, no es necesario que lo asigne definitivamente el destinatario. Un parámetro `ref` de un tipo de matriz puede cambiar como resultado de la llamada. Por ejemplo, a la matriz se le puede asignar el valor [NULL](../../../csharp/language-reference/keywords/null.md) o se puede inicializar en otra matriz. Por ejemplo:  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 En los dos ejemplos siguientes se muestra la diferencia entre `out` y `ref` cuando se usan para pasar matrices a métodos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la matriz `theArray` se declara en el llamador (el método `Main`) y se inicializa en el método `FillArray`. A continuación, los elementos de la matriz se devuelven al llamador y se muestran.  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la matriz `theArray` se inicializa en el llamador (el método `Main`) y se pasa al método `FillArray` mediante el parámetro `ref`. Algunos de los elementos de la matriz se actualizan en el método `FillArray`. A continuación, los elementos de la matriz se devuelven al llamador y se muestran.  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a>Vea también  
 [ref](../../../csharp/language-reference/keywords/ref.md)  
 [Modificador del parámetro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)
