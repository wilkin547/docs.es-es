---
title: "stackalloc (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "stackalloc_CSharpKeyword"
  - "stackalloc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "stackalloc (palabra clave) [C#]"
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# stackalloc (Referencia de C#)
La palabra clave `stackalloc` se utiliza en un contexto de código no seguro para asignar un bloque de memoria en la pila.  
  
```  
int* block = stackalloc int[100];  
```  
  
## Comentarios  
 La palabra clave solo es válida en inicializadores de variable locales.  El siguiente código provoca errores de compilación.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Dado que intervienen los tipos de puntero, `stackalloc` requiere el contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  Para obtener más información, vea [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 `stackalloc` es como [\_alloca](/visual-cpp/c-runtime-library/reference/alloca) en la biblioteca de tiempo de ejecución C.  
  
 En el ejemplo siguiente se calculan y se muestran los primeros 20 números de la secuencia de Fibonacci.  Cada número es la suma de los dos números anteriores.  En el código, un bloque de memoria de tamaño suficiente para contener 20 elementos de tipo `int` se asigna en la pila y no en el montón.  La dirección del bloque se almacena en el puntero `fib`.  Esta memoria no está sometida a la recolección de elementos no utilizados y, por lo tanto, no necesita anclarse \(mediante el uso de [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)\).  La duración del bloque de memoria se limita a la duración del método que lo define.  No hay forma de liberar la memoria antes de la devolución del método.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#15)]  
  
## Seguridad  
 El código no seguro es menos seguro que las alternativas seguras.  Sin embargo, el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en Common Language Runtime \(CLR\).  Si se detecta una saturación del búfer, el proceso se finaliza tan rápidamente como sea posible para reducir la oportunidad de que se ejecute código malintencionado.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)