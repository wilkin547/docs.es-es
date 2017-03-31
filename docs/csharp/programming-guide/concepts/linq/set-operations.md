---
title: Operaciones set (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 37841cde3aa5e4aaa6545b3a160422d024be5842
ms.lasthandoff: 03/13/2017

---
# <a name="set-operations-c"></a>Operaciones set (C#)
Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).  
  
 Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Distinct|Quita valores duplicados de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|Except|Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.|No es aplicable.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|Formar intersección|Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.|No es aplicable.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|Unión|Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.|No es aplicable.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a>Comparación de operaciones set  
  
### <a name="distinct"></a>Distinct  
 La siguiente ilustración muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> en una secuencia de caracteres. La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.  
  
 ![Gráfico que muestra el comportamiento de Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")  
  
### <a name="except"></a>Except  
 La siguiente ilustración muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>. La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.  
  
 ![Gráfico que muestra la acción de Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")  
  
### <a name="intersect"></a>Formar intersección  
 La siguiente ilustración muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>. La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.  
  
 ![Gráfico que muestra la intersección de dos secuencias.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Unión  
 En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres. La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.  
  
 ![Gráfico que muestra la unión de dos secuencias.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [How to: Combine and Compare String Collections (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  (Cómo: Combinar y comparar colecciones de cadenas (LINQ) [C#])  
 [How to: Find the Set Difference Between Two Lists (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md) (Cómo: Buscar la diferencia de conjuntos entre dos listas (LINQ) [C#])
