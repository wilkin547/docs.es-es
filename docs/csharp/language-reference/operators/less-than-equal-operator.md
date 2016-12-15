---
title: "Operador &lt;= (Referencia de C#) | Microsoft Docs"
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
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= (operador) [C#]"
  - "<= (operador menor o igual que) [C#]"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador &lt;= (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Todos los tipos numéricos y de enumeración definen un operador relacional "menor o igual que" \(`<=`\) que devuelve `true` si el primer operando es menor o igual que el segundo y devuelve `false` en caso contrario.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `<=` Para obtener más información, vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Si se sobrecarga `<=`, también se debe sobrecargar [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [explícita](../../../csharp/language-reference/keywords/explicit.md)