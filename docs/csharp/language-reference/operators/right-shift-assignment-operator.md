---
title: "&gt;&gt;= (operador) (Referencia de C#) | Microsoft Docs"
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
  - ">>=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">>= (operador de asignación y desplazamiento a la derecha) [C#]"
  - "operador de asignación y desplazamiento a la derecha (>>=) [C#]"
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &gt;&gt;= (operador) (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación y desplazamiento a la derecha.  
  
## Comentarios  
 Una expresión de la forma  
  
```  
x >>= y  
```  
  
 se evalúa como  
  
```  
x = x >> y  
```  
  
 salvo que `x` sólo se evalúa una vez.  El [operador \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) desplaza `x` a la derecha el número de bits especificado por `y`.  
  
 El operador \>\>\= no se puede sobrecargar directamente, pero los tipos definidos por el usuario sí pueden sobrecargar el [operador \>\>](../../../csharp/language-reference/operators/right-shift-operator.md) \(vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Ejemplo  
 [!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)