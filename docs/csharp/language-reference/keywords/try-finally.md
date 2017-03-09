---
title: "try-finally (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "finally"
  - "finally_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "finally (palabra clave) [C#]"
  - "try-finally (instrucción) [C#]"
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# try-finally (Referencia de C#)
Utilizando un bloque `finally`, puede limpiar los recursos que se asignan en un bloque [try](../../../csharp/language-reference/keywords/try-catch.md), y puede ejecutar código incluso si se produce una excepción en el bloque `try`.  Normalmente, las instrucciones de un bloque `finally` se ejecuta cuando el control sale de una instrucción `try`.  La transferencia del control puede producirse como resultado de la ejecución normal, de la ejecución de la instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try` .  
  
 Dentro de una excepción controlada, se garantiza que el bloque asociado `finally` pueda ejecutarse.  Sin embargo, si la excepción no se controla, la ejecución del bloque de `finally` depende de cómo se desencadena la operación de desenredo de excepción.  Esto, a su vez, depende de cómo se configurar el equipo.  Para obtener más información, vea [Procesamiento de excepciones no controladas en CLR](http://go.microsoft.com/fwlink/?LinkId=128371).  
  
 Normalmente, cuando una excepción no controlada finaliza una aplicación, si se ejecuta o no el bloque `finally` no es importante.  Sin embargo, si tiene instrucciones en un `finally` bloqueado que debe ejecutarse incluso en esa situación, una solución es agregar un `catch` bloqueado a la instrucción `try`\-`finally`.  Alternativamente, puede detectar la excepción que se produzca en el bloque `try` de una instrucción `try`\- de`finally` situada más arriba de la pila de llamadas.  Es decir, puede detectar la excepción en el método que llama al método que contiene la instrucción de `try`\- de`finally`, o en el método que llama a ese método, o en cualquier método de la pila de llamadas.  Si la excepción no se detecta, la ejecución del bloque de `finally` depende de si el sistema operativo elige desencadenar una operación de desenredo de excepción.  
  
## Ejemplo  
 En el ejemplo siguiente, una instrucción no válida de conversión provoca una excepción de `System.InvalidCastException`.  La excepción es no controlada.  
  
 [!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/csharp/try-finally_1.cs)]  
  
 En el ejemplo siguiente, una excepción del método de `TryCast` se detecta en un método más arriba en la pila de llamadas.  
  
 [!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/csharp/try-finally_2.cs)]  
  
 Para obtener más información acerca de `finally`, vea [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C\# también contiene la [instrucción using](../../../csharp/language-reference/keywords/using-statement.md), que proporciona funcionalidad similar para los objetos <xref:System.IDisposable> en una sintaxis adecuada.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Instrucciones try, throw y catch \(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Cómo: Iniciar excepciones explícitamente](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)