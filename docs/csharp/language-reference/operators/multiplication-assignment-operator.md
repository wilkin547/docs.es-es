---
title: "Operador *= (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "*=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "*= (operador) [C#]"
  - "*= (operador de asignación y multiplicación binaria) [C#]"
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operador *= (Referencia de C#)
El operador de asignación y multiplicación binario.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `*=`, por ejemplo  
  
```  
x *= y  
```  
  
 es equivalente a  
  
```  
x = x * y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador \*](../../../csharp/language-reference/operators/multiplication-operator.md) está predefinido con la multiplicación para tipos numéricos.  
  
 El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \*](../../../csharp/language-reference/operators/multiplication-operator.md) \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#13)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)