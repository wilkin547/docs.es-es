---
title: "do (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "do_CSharpKeyword"
  - "do"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "do (palabra clave) [C#]"
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# do (Referencia de C#)
La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una determinada expresión se evalúa como `false`.  El cuerpo del bucle se debe incluir entre llaves, `{}`, a menos que esté compuesto por una sola instrucción.  En ese caso, las llaves son opcionales.  
  
## Ejemplo  
 En el ejemplo siguiente las instrucciones de bucle `do-while` se ejecutan con la condición de que la variable `x` sea menor que 5.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.  
  
 En cualquier punto del bloque `do-while`, puede salir del bucle utilizando la instrucción [break](../../../csharp/language-reference/keywords/break.md).  Puede pasar directamente a la instrucción de evaluación de expresión `while` utilizando la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).  Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción tras el bucle .  Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción detrás del bucle `do-while`.  
  
 También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [do\-while \(instrucción de C\+\+\)](/visual-cpp/cpp/do-while-statement-cpp)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)