---
description: 'Más información acerca de: sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)'
title: Sintaxis de las expresiones de consulta para operadores de consulta estándar
ms.date: 07/20/2015
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
ms.openlocfilehash: c891482506f45278d9ecbe037a516b3de3fe97b7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100477494"
---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)

Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen dedicado Visual Basic sintaxis de palabras clave del lenguaje que permite que se llamen como parte de una *expresión de consulta*. Una expresión de consulta constituye una forma diferente de expresar una consulta, más legible que su equivalente *basada en métodos*. Las cláusulas de las expresiones de consulta se convierten en llamadas a los métodos de consulta en tiempo de compilación.  
  
## <a name="query-expression-syntax-table"></a>Tabla de sintaxis de expresiones de consulta  

 En la tabla siguiente se muestran los operadores de consulta estándar que poseen cláusulas de expresiones de consulta equivalentes.  
  
|Método|Visual Basic sintaxis de expresiones de consulta|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> (Para obtener más información, vea [cláusula FROM](../../../language-reference/queries/from-clause.md)).|  
|<xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> (Para obtener más información, vea [DISTINCT (cláusula](../../../language-reference/queries/distinct-clause.md))).|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> (Para obtener más información, vea [cláusula Group by](../../../language-reference/queries/group-by-clause.md)).|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> (Para obtener más información, vea [cláusula Group join](../../../language-reference/queries/group-join-clause.md)).|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> o bien<br /><br /> `Join … [As …]In … On …`<br /><br /> (Para obtener más información, vea [cláusula join](../../../language-reference/queries/join-clause.md)).|  
|<xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> (Para obtener más información, vea [cláusula order by](../../../language-reference/queries/order-by-clause.md)).|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> (Para obtener más información, vea [cláusula order by](../../../language-reference/queries/order-by-clause.md)).|  
|<xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (Para obtener más información, vea [cláusula SELECT](../../../language-reference/queries/select-clause.md)).|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Varias `From` cláusulas<br /><br /> (Para obtener más información, vea [cláusula FROM](../../../language-reference/queries/from-clause.md)).|  
|<xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> (Para obtener más información, vea la [cláusula SKIP](../../../language-reference/queries/skip-clause.md)).|  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> (Para obtener más información, vea la [cláusula SKIP while](../../../language-reference/queries/skip-while-clause.md)).|  
|<xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> (Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md)).|  
|<xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> (Para obtener más información, consulte [Take (cláusula](../../../language-reference/queries/take-clause.md))).|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> (Para obtener más información, vea [Take while (cláusula](../../../language-reference/queries/take-while-clause.md))).|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> (Para obtener más información, vea [cláusula order by](../../../language-reference/queries/order-by-clause.md)).|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> (Para obtener más información, vea [cláusula order by](../../../language-reference/queries/order-by-clause.md)).|  
|<xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> (Para obtener más información, vea la [cláusula WHERE](../../../language-reference/queries/where-clause.md)).|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)](classification-of-standard-query-operators-by-manner-of-execution.md)
