---
title: "continue (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "continue_CSharpKeyword"
  - "continue"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "continue (palabra clave) [C#]"
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# continue (Referencia de C#)
La instrucción de `continue` pasa el control a la siguiente iteración de [mientras](../../../csharp/language-reference/keywords/while.md) que agrega, de [haga](../../../csharp/language-reference/keywords/do.md), de [para](../../../csharp/language-reference/keywords/for.md), o la instrucción de [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.  
  
## Ejemplo  
 En este ejemplo, un contador se inicializa para contar de 1 a 10.  Mediante la instrucción de `continue` junto con la expresión `(i < 9)`, las instrucciones entre `continue` y el final del cuerpo de `for` se omiten.  
  
 [!code-cs[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [break \(Instrucción\)](/visual-cpp/cpp/break-statement-cpp)   
 [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)