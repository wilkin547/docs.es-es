---
title: stackalloc (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 337a06daaf36a1eb265f66cd191fc48b80f0bae1
ms.lasthandoff: 03/13/2017

---
# <a name="stackalloc-c-reference"></a>stackalloc (Referencia de C#)
La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave solo es válida en inicializadores de variables locales. El código siguiente genera errores del compilador.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Como implica tipos de puntero, `stackalloc` requiere contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md). Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).  
  
 `stackalloc` es como [_alloca](https://docs.microsoft.com/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.  
  
 En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci. Cada número es la suma de los dos números anteriores. En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`. La dirección del bloque se almacena en el puntero `fib`. Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)). La duración del bloque de memoria se limita a la duración del método que lo define. No se puede liberar la memoria antes de que el método vuelva.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a>Seguridad  
 El código no seguro es menos seguro que las alternativas seguras. Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md)  (Palabras clave de operador [Referencia de C#])  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
