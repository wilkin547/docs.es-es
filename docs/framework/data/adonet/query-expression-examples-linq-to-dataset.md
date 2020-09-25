---
title: Ejemplos de expresiones de consultas (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
ms.openlocfilehash: 1671769871d8c224391a34f5a6294bb6015cafdc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177376"
---
# <a name="query-expression-examples-linq-to-dataset"></a><span data-ttu-id="163a4-102">Ejemplos de expresiones de consultas (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="163a4-102">Query Expression Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="163a4-103">En esta sección se proporcionan ejemplos de programación de LINQ to DataSet en la sintaxis de expresiones de consulta que utilizan los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="163a4-103">This section provides LINQ to DataSet programming examples in query expression syntax that use the standard query operators.</span></span> <span data-ttu-id="163a4-104">El <xref:System.Data.DataSet> usado en estos ejemplos se rellena con el `FillDataSet` método, que se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="163a4-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="163a4-105">Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="163a4-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="163a4-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="163a4-106">In This Section</span></span>  

 [<span data-ttu-id="163a4-107">Proyección</span><span class="sxs-lookup"><span data-stu-id="163a4-107">Projection</span></span>](query-expression-syntax-examples-projection-linq-to-dataset.md)  
 <span data-ttu-id="163a4-108">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="163a4-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="163a4-109">Restricción</span><span class="sxs-lookup"><span data-stu-id="163a4-109">Restriction</span></span>](query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 <span data-ttu-id="163a4-110">Los ejemplos de este tema muestran cómo usar el método <xref:System.Linq.Enumerable.Where%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="163a4-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="163a4-111">Partitioning</span><span class="sxs-lookup"><span data-stu-id="163a4-111">Partitioning</span></span>](query-expression-syntax-examples-partitioning.md)  
 <span data-ttu-id="163a4-112">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A> para consultar un <xref:System.Data.DataSet> y particionar los resultados.</span><span class="sxs-lookup"><span data-stu-id="163a4-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="163a4-113">Ordenación</span><span class="sxs-lookup"><span data-stu-id="163a4-113">Ordering</span></span>](query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="163a4-114">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenByDescending%2A> para consultar un <xref:System.Data.DataSet> y ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="163a4-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="163a4-115">Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="163a4-115">Element Operators</span></span>](query-expression-syntax-examples-element-operators.md)  
 <span data-ttu-id="163a4-116">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="163a4-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="163a4-117">Operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="163a4-117">Aggregate Operators</span></span>](query-expression-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="163a4-118">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar <xref:System.Data.DataSet> y agregar datos.</span><span class="sxs-lookup"><span data-stu-id="163a4-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="163a4-119">Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="163a4-119">Join Operators</span></span>](query-expression-syntax-examples-join-operators.md)  
 <span data-ttu-id="163a4-120">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="163a4-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163a4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="163a4-121">See also</span></span>

- [<span data-ttu-id="163a4-122">Ejemplos de consultas basadas en métodos</span><span class="sxs-lookup"><span data-stu-id="163a4-122">Method-Based Query Examples</span></span>](method-based-query-examples-linq-to-dataset.md)
- [<span data-ttu-id="163a4-123">Ejemplos de operadores específicos de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="163a4-123">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="163a4-124">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="163a4-124">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
