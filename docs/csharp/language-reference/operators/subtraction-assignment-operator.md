---
title: "/= (operador) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (operador de asignación y división) [C#]"
  - "operador de asignación y división (/=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /= (operador) (Referencia de C#)
El operador de asignación y división.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `/=`, por ejemplo  
  
```  
x /= y  
```  
  
 es equivalente a  
  
```  
x = x / y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador \/](../../../csharp/language-reference/operators/division-operator.md) está predefinido con la división para tipos numéricos.  
  
 El operador `/=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \/](../../../csharp/language-reference/operators/division-operator.md) \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  En todos los operadores de asignación compuesta, al sobrecargar el operador binario implícitamente se sobrecarga la asignación compuesta equivalente.  
  
## Ejemplo  
 [!code-cs[csRefOperators#5](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#5)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)