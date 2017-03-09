---
title: "|= (operador) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "|=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|= (operador de asignación y OR) [C#]"
  - "operador de asignación y OR (|=) [C#]"
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# |= (operador) (Referencia de C#)
El operador de asignación OR.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `|=`, por ejemplo  
  
```  
x |= y  
```  
  
 es equivalente a  
  
```  
x = x | y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) realiza una operación lógica OR bit a bit sobre operandos integrales y una operación lógica OR sobre operandos de tipo bool.  
  
 El operador `|=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador &#124;](../../../csharp/language-reference/operators/or-operator.md) \(vea [operator \(Referencia de C\#](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#10)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)