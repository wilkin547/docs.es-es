---
title: stackalloc (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b9c5328bfa1b0fc9a7751763c7d728096886905
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2018
---
# <a name="stackalloc-c-reference"></a>stackalloc (Referencia de C#)
La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.  
  
```csharp  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave solo es válida en inicializadores de variables locales. El código siguiente genera errores del compilador.  
  
```csharp  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Como implica tipos de puntero, `stackalloc` requiere contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md). Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).  
  
 `stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.  
  
 En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci. Cada número es la suma de los dos números anteriores. En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`. La dirección del bloque se almacena en el puntero `fib`. Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)). La duración del bloque de memoria se limita a la duración del método que lo define. No se puede liberar la memoria antes de que el método vuelva.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a>Seguridad  
 El código no seguro es menos seguro que las alternativas seguras. Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
