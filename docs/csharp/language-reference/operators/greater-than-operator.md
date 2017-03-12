---
title: "Operador &gt; (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "> (operador) [C#]"
  - "> (operador mayor que) [C#]"
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operador &gt; (Referencia de C#)
Todos los tipos numéricos y de enumeración definen un operador relacional "mayor que" \(`>`\) que devuelve `true` si el primer operando es mayor que el segundo y `false` en caso contrario.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `>` \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  Si se sobrecarga `>`, también se debe sobrecargar [\<](../../../csharp/language-reference/operators/less-than-operator.md).  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#29)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [explícita](../../../csharp/language-reference/keywords/explicit.md)