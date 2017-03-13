---
title: "Operador | (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "|_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "| (operador) [C#]"
  - "| (operador binario) [C#]"
  - "OR (operador bit a bit) [C#]"
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Operador | (Referencia de C#)
Binary        `|`  están predefinidos para los tipos enteros y `bool`.  Para los tipos enteros,  `|`calcula la operación OR bit a bit de sus operandos.  Para los operandos de tipo `bool`.  `|` calcula la operación lógica OR de sus operandos; es decir, el resultado es `false` si, y solo si, ambos operandos son `false`.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador          `|` \(vea [operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)