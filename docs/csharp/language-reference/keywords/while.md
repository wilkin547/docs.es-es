---
title: "while (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "while_CSharpKeyword"
  - "while"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "while (palabra clave) [C#]"
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# while (Referencia de C#)
La instrucción `while` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/csharp/while_1.cs)]  
  
## Ejemplo  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/csharp/while_2.cs)]  
  
## Ejemplo  
 Como la comprobación de la expresión `while` tiene lugar antes de la ejecución del bucle, las instrucciones internas de un bucle `while` pueden no llegar a ejecutarse.  Esto es diferente del bucle [do](../../../csharp/language-reference/keywords/do.md) que se ejecuta una o varias veces.  
  
 Un bucle `while` se puede terminar cuando una instrucción [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) transfiere el control fuera del bucle.  Para pasar el control a la siguiente iteración sin salir del bucle, use la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).  Observe la diferencia en los resultados de los tres ejemplos anteriores con relación a dónde se incrementa `int n`.  En el ejemplo siguiente no se genera ningún resultado.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/csharp/while_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [while \(Instrucción\) \(C\+\+\)](/visual-cpp/cpp/while-statement-cpp)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)