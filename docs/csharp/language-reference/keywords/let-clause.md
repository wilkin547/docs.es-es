---
title: "let (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
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
  - "let_CSharpKeyword"
  - "let"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "let (cláusula) [C#]"
  - "let (palabra clave) [C#]"
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# let (Cl&#225;usula, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para utilizarlo en cláusulas posteriores.  Para ello, puede utilizar la palabra clave `let`, que crea una nueva variable de rango y la inicializa con el resultado de la expresión que proporcione.  Al inicializarse con un valor, la variable de rango no puede utilizarse para almacenar otro valor.  Sin embargo, si la variable de rango contiene un tipo que se puede consultar, puede realizarse una consulta en ésta.  
  
## Ejemplo  
 En el ejemplo siguiente, `let` se utiliza de dos formas:  
  
1.  Para crear un tipo enumerable que se puede consultar.  
  
2.  Para habilitar que la consulta llame a `ToLower` sólo una vez en la variable de rango `word`.  Si no utiliza `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.  
  
 [!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Cómo: Controlar excepciones en expresiones de consulta](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)