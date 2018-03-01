---
title: "Pasar matrices como argumentos (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f152173b747a171052ab99f261ed91ced9465fdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Pasar matrices como argumentos (Guía de programación de C#)
Las matrices se pueden pasar como argumentos a parámetros de método. Dado que las matrices son tipos de referencia, el método puede cambiar el valor de los elementos.  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>Pasar matrices unidimensionales como argumentos  
 Puede pasar una matriz unidimensional inicializada a un método. Por ejemplo, la siguiente instrucción envía una matriz a un método de impresión.  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 En el siguiente código, se muestra una implementación parcial del método de impresión.  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente, una matriz de cadenas se inicializa y pasa como un argumento a un método `PrintArray` para cadenas. El método muestra los elementos de la matriz. Después, se llama a los métodos `ChangeArray` y `ChangeArrayElement` para demostrar que enviar un argumento de matriz en función del valor no evita los cambios a los elementos de matriz.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>Pasar matrices multidimensionales como argumentos  
 Pase una matriz multidimensional inicializada a un método de la misma manera que pasa una matriz unidimensional.  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 En el código siguiente, se muestra una declaración parcial de un método de impresión que acepta una matriz bidimensional como su argumento.  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 Puede inicializar y pasar una nueva matriz en un solo paso, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente, una matriz bidimensional de enteros se inicializa y pasa al método `Print2DArray`. El método muestra los elementos de la matriz.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)
