---
title: "Operador &amp;= (Referencia de C#) | Microsoft Docs"
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
  - "&=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&= (operador) [C#]"
  - "&|= (operador de asignación y AND) [C#]"
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador &amp;= (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación y AND.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `&=`, por ejemplo  
  
```  
x &= y  
```  
  
 es equivalente a  
  
```  
x = x & y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador &](../../../csharp/language-reference/operators/and-operator.md) realiza una operación AND bit a bit lógica sobre operandos integrales y una operación AND lógica sobre operandos `bool`.  
  
 El operador `&=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador &](../../../csharp/language-reference/operators/and-operator.md) binario \(vea [operator \(Referencia de C\#](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)