---
title: "Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 30e994329234b8bd455f739694e50121bac63d5d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a><span data-ttu-id="289a3-102">Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="289a3-102">Query Expression Syntax for Standard Query Operators (C#)</span></span>
<span data-ttu-id="289a3-103">Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave de lenguaje C# para que se puedan invocar como parte de una *expresión de consulta*.</span><span class="sxs-lookup"><span data-stu-id="289a3-103">Some of the more frequently used standard query operators have dedicated C# language keyword syntax that enables them to be called as part of a *query expression*.</span></span> <span data-ttu-id="289a3-104">Una expresión de consulta constituye una forma diferente de expresar una consulta, más legible que su equivalente *basada en métodos*.</span><span class="sxs-lookup"><span data-stu-id="289a3-104">A query expression is a different, more readable form of expressing a query than its *method-based*  equivalent.</span></span> <span data-ttu-id="289a3-105">Las cláusulas de las expresiones de consulta se convierten en llamadas a los métodos de consulta en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="289a3-105">Query expression clauses are translated into calls to the query methods at compile time.</span></span>  
  
## <a name="query-expression-syntax-table"></a><span data-ttu-id="289a3-106">Tabla de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="289a3-106">Query Expression Syntax Table</span></span>  
 <span data-ttu-id="289a3-107">En la tabla siguiente se muestran los operadores de consulta estándar que poseen cláusulas de expresiones de consulta equivalentes.</span><span class="sxs-lookup"><span data-stu-id="289a3-107">The following table lists the standard query operators that have equivalent query expression clauses.</span></span>  
  
|<span data-ttu-id="289a3-108">Método</span><span class="sxs-lookup"><span data-stu-id="289a3-108">Method</span></span>|<span data-ttu-id="289a3-109">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="289a3-109">C# Query Expression Syntax</span></span>|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|<span data-ttu-id="289a3-110">Use una variable de rango con tipo explícito, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="289a3-110">Use an explicitly typed range variable, for example:</span></span><br /><br /> `from int i in numbers`<br /><br /> <span data-ttu-id="289a3-111">(Para obtener más información, vea [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-111">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> <span data-ttu-id="289a3-112">O bien</span><span class="sxs-lookup"><span data-stu-id="289a3-112">-or-</span></span><br /><br /> `group … by … into …`<br /><br /> <span data-ttu-id="289a3-113">(Para obtener más información, vea [Cláusula group](../../../../csharp/language-reference/keywords/group-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-113">(For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> <span data-ttu-id="289a3-114">(Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../../csharp/language-reference/keywords/join-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-114">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> <span data-ttu-id="289a3-115">(Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../../csharp/language-reference/keywords/join-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-115">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> <span data-ttu-id="289a3-116">(Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-116">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> <span data-ttu-id="289a3-117">(Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-117">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> <span data-ttu-id="289a3-118">(Para obtener más información, vea [Cláusula select](../../../../csharp/language-reference/keywords/select-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-118">(For more information, see [select clause](../../../../csharp/language-reference/keywords/select-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<span data-ttu-id="289a3-119">Varias cláusulas `from`.</span><span class="sxs-lookup"><span data-stu-id="289a3-119">Multiple `from` clauses.</span></span><br /><br /> <span data-ttu-id="289a3-120">(Para obtener más información, vea [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-120">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> <span data-ttu-id="289a3-121">(Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-121">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> <span data-ttu-id="289a3-122">(Para obtener más información, vea [orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-122">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> <span data-ttu-id="289a3-123">(Para obtener más información, vea [where (Cláusula)](../../../../csharp/language-reference/keywords/where-clause.md)).</span><span class="sxs-lookup"><span data-stu-id="289a3-123">(For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="289a3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="289a3-124">See Also</span></span>  
 <span data-ttu-id="289a3-125"><xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="289a3-125"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="289a3-126"><xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="289a3-126"><xref:System.Linq.Queryable></span></span>   
 <span data-ttu-id="289a3-127">[Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="289a3-127">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="289a3-128">Clasificación de operadores de consulta estándar por modo de ejecución (C#)</span><span class="sxs-lookup"><span data-stu-id="289a3-128">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)

