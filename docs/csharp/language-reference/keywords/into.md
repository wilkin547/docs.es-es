---
title: "into (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "into_CSharpKeyword"
  - "into"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "into (palabra clave) [C#]"
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# into (Referencia de C#)
La palabra clave contextual `into` puede utilizarse para crear un identificador temporal que almacene los resultados de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) o [select](../../../csharp/language-reference/keywords/select-clause.md) en un nuevo identificador.  Este mismo identificador puede ser un generador de comandos de consulta adicionales.  Cuando se utiliza en una cláusula `group` o `select`, a veces se hace referencia al uso del nuevo identificador como *continuación*.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el uso de la palabra clave `into` para habilitar un identificador temporal `fruitGroup` que tiene un tipo deducido de `IGrouping`.  Con el identificador puede invocar el método <xref:System.Linq.Enumerable.Count%2A> en cada grupo y seleccionar solamente aquellos grupos que contengan dos o más palabras.  
  
 [!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 El uso de `into` en una cláusula `group` sólo es necesario cuando desea realizar operaciones de consulta adicionales en cada grupo.  Para obtener más información, consulte [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Para obtener un ejemplo del uso de `into` en una cláusula `join`, vea [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md).  
  
## Vea también  
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md)