---
title: "|= (operador) (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
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
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# |= (operador) (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

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
 [!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)