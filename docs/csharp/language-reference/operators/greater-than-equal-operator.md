---
title: "Operador &gt;= (Referencia de C#) | Microsoft Docs"
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
  - ">=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">= (operador) [C#]"
  - ">= (operador mayor o igual que) [C#]"
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador &gt;= (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Todos los tipos numéricos y de enumeración definen un operador relacional "mayor o igual que" \(`>=`\) que devuelve `true` si el primer operando es mayor o igual que el segundo, y devuelve `false` en caso contrario.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `>=` Para obtener más información, vea [operator \(Referencia de C\#\)](../../../csharp/language-reference/keywords/operator.md)\).  Si se sobrecarga `>=`, también se debe sobrecargar [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)