---
title: "orderby (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
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
  - "orderby"
  - "orderby_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cláusula orderby [C#]"
  - "orderby (palabra clave) [C#]"
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# orderby (Cl&#225;usula, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En una expresión de consulta, la cláusula `orderby` hace que a la secuencia o subsecuencia \(grupo\) que se devuelve se le aplique una ordenación ascendente o descendente.  Se pueden especificar varias claves para realizar una o varias operaciones de ordenación secundarias.  El comparador predeterminado realiza la ordenación para el tipo del elemento.  El criterio de ordenación predeterminado es el ascendente.  También puede especificar un comparador personalizado.  Sin embargo, sólo está disponible utilizando la sintaxis basada en métodos.  Para obtener más información, vea [Sorting Data](../../../visual-basic/programming-guide/concepts/linq/sorting-data.md).  
  
## Ejemplo  
 En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético empezando por la A y la segunda consulta ordena las mismas palabras en orden descendente.  \(La palabra clave `ascending` es el valor de ordenación predeterminado y se puede omitir.\)  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se realiza una ordenación primaria de los apellidos de los alumnos y, a continuación, una ordenación secundaria de sus nombres.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## Comentarios  
 En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>.  Varias claves de la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)