---
title: "Operador ^= (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^= (operador) [C#]"
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operador ^= (Referencia de C#)
El operador de asignación y OR exclusivo.  
  
## Comentarios  
 Una expresión de la forma  
  
```  
x ^= y  
```  
  
 se evalúa como  
  
```  
x = x ^ y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador ^](../../../csharp/language-reference/operators/xor-operator.md) realiza una operación OR exclusiva bit a bit sobre operandos integrales y una operación OR exclusiva lógica sobre operandos de tipo [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 El operador ^\= no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador ^](../../../csharp/language-reference/operators/xor-operator.md) \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#23)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)