---
title: "Operador &lt; (Referencia de C#) | Microsoft Docs"
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
  - "<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "< (operador) [C#]"
  - "< (operador menor que) [C#]"
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador &lt; (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Todos los tipos numéricos y de enumeración definen un operador relacional "menor que" \(`<`\) que devuelve `true` si el primer operando es menor que el segundo y `false` en caso contrario.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `<` \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  Si se sobrecarga `<`, también se debe sobrecargar [\>](../../../csharp/language-reference/operators/greater-than-operator.md).  Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si existe, también se sobrecarga de modo implícito.  
  
## Ejemplo  
 [!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)