---
title: "%= (operador) (Referencia de C#) | Microsoft Docs"
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
  - "%=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "%= (operador de asignación y módulo) [C#]"
  - "operador de asignación y módulo (=%) [C#]"
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# %= (operador) (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación del resto.  
  
## Comentarios  
 Una expresión que utiliza el operador de asignación `%=`, por ejemplo  
  
```  
x %= y  
```  
  
 es equivalente a  
  
```  
x = x % y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador %](../../../csharp/language-reference/operators/modulus-operator.md) está predefinido en tipos numéricos para calcular el resto de la división.  
  
 El operador `%=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador %](../../../csharp/language-reference/operators/modulus-operator.md) \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)