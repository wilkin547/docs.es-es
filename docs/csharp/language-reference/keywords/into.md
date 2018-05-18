---
title: into (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 9bc7d50b77fe42861f92cc5bec946678d11d73d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="into-c-reference"></a>into (Referencia de C#)
La palabra clave contextual `into` puede usarse para crear un identificador temporal para almacenar los resultados de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) o [select](../../../csharp/language-reference/keywords/select-clause.md) en un nuevo identificador. Este identificador puede ser un generador de comandos de consulta adicionales. Cuando se usa en una cláusula `group` o `select`, el uso del nuevo identificador se denomina a veces una *continuación*.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestra el uso de la palabra clave `into` para habilitar un identificador temporal `fruitGroup` que tiene un tipo deducido de `IGrouping`. Mediante el identificador, puede invocar el método <xref:System.Linq.Enumerable.Count%2A> en cada grupo y seleccionar solo los grupos que contienen dos o más palabras.  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 El uso de `into` en una cláusula `group` solo es necesario cuando quiere realizar operaciones de consulta adicionales en cada grupo. Para obtener más información, vea [group (Cláusula)](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Para obtener un ejemplo del uso de `into` en una cláusula `join`, vea [join (Cláusula)](../../../csharp/language-reference/keywords/join-clause.md).  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [group (cláusula)](../../../csharp/language-reference/keywords/group-clause.md)
