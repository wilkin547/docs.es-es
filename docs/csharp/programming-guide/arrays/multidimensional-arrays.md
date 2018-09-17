---
title: Matrices multidimensionales (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a1d7a0a014c330682316e869f6727082fa3b31ef
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45668059"
---
# <a name="multidimensional-arrays-c-programming-guide"></a>Matrices multidimensionales (Guía de programación de C#)

Las matrices pueden tener varias dimensiones. Por ejemplo, la siguiente declaración crea una matriz bidimensional de cuatro filas y dos columnas.  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 La siguiente declaración crea una matriz de tres dimensiones, 4, 2 y 3.  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Inicialización de matriz

 La matriz se puede inicializar en la declaración como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 También se puede inicializar la matriz sin especificar el intervalo.  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Si opta por declarar una variable de matriz sin inicializarla, deberá usar el operador `new` para asignar una matriz a la variable. El uso de `new` se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 En el ejemplo siguiente se asigna un valor a un elemento de matriz determinado.  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 De igual forma, en el ejemplo siguiente se obtiene el valor de un elemento de matriz determinado y se asigna a la variable `elementValue`.  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 El ejemplo de código siguiente inicializa los elementos de matriz con valores predeterminados (salvo las matrices escalonadas).  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Matrices](../../../csharp/programming-guide/arrays/index.md)  
- [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)
