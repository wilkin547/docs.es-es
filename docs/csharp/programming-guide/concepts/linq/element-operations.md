---
title: Operaciones de elementos (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 55081e66419624c2c4930a254d3d464007477766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="element-operations-c"></a>Operaciones de elementos (C#)
Las operaciones de elementos devuelven un único elemento específico de una secuencia.  
  
 Los métodos del operador de consulta estándar que realizan operaciones de elementos se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|Devuelve el elemento situado en un índice especificado de la colección.|No es aplicable.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=nameWithType>|  
|ElementAtOrDefault|Devuelve el elemento situado en un índice especificado de una colección o un valor predeterminado si el índice está fuera del intervalo.|No es aplicable.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=nameWithType>|  
|First|Devuelve el primer elemento de una colección, o el primer elemento que cumple una condición.|No es aplicable.|<xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=nameWithType>|  
|FirstOrDefault|Devuelve el primer elemento de una colección, o el primer elemento que cumple una condición. Devuelve un valor predeterminado si dicho elemento no existe.|No es aplicable.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=nameWithType>|  
|Último|Devuelve el último elemento de una colección, o el último elemento que cumple una condición.|No es aplicable.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=nameWithType>|  
|LastOrDefault|Devuelve el último elemento de una colección, o el último elemento que cumple una condición. Devuelve un valor predeterminado si dicho elemento no existe.|No es aplicable.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=nameWithType>|  
|Single|Devuelve el único elemento de una colección, o el único elemento que cumple una condición.|No es aplicable.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=nameWithType>|  
|SingleOrDefault|Devuelve el único elemento de una colección, o el único elemento que cumple una condición. Devuelve un valor predeterminado si dicho elemento no existe o si la colección no contiene exactamente un elemento.|No es aplicable.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>  
 [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))  
 [Cómo: Buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
