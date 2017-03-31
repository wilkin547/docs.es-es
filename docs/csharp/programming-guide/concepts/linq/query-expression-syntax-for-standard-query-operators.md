---
title: "Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#) | Microsoft Docs"
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
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
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
ms.openlocfilehash: 115f97eec99d5f22a659532ccf4ed7b20a089014
ms.lasthandoff: 03/13/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)
Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave de lenguaje C# para que se puedan invocar como parte de una *expresión de consulta*. Una expresión de consulta constituye una forma diferente de expresar una consulta, más legible que su equivalente *basada en métodos*. Las cláusulas de las expresiones de consulta se convierten en llamadas a los métodos de consulta en tiempo de compilación.  
  
## <a name="query-expression-syntax-table"></a>Tabla de sintaxis de expresiones de consulta  
 En la tabla siguiente se muestran los operadores de consulta estándar que poseen cláusulas de expresiones de consulta equivalentes.  
  
|Método|Sintaxis de la expresión de consulta de C#|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|Use una variable de rango con tipo explícito, por ejemplo:<br /><br /> `from int i in numbers`<br /><br /> (Para obtener más información, vea [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md)).|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> O bien<br /><br /> `group … by … into …`<br /><br /> (Para obtener más información, vea [Cláusula group](../../../../csharp/language-reference/keywords/group-clause.md)).|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> (Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../../csharp/language-reference/keywords/join-clause.md)).|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> (Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../../csharp/language-reference/keywords/join-clause.md)).|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> (Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> (Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> (Para obtener más información, vea [Cláusula select](../../../../csharp/language-reference/keywords/select-clause.md)).|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Varias cláusulas `from`.<br /><br /> (Para obtener más información, vea [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md)).|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> (Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> (Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> (Para obtener más información, vea [where (Cláusula)](../../../../csharp/language-reference/keywords/where-clause.md)).|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable>   
 [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))  
 [Clasificación de operadores de consulta estándar por modo de ejecución (C#)](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
