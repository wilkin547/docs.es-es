---
description: 'Más información acerca de: ejemplos de expresiones de consulta (LINQ to DataSet)'
title: Ejemplos de expresiones de consultas (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
ms.openlocfilehash: 1d1571a851fae685942cbdbd557b275e86e8b0d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663695"
---
# <a name="query-expression-examples-linq-to-dataset"></a><span data-ttu-id="9f101-103">Ejemplos de expresiones de consultas (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9f101-103">Query Expression Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="9f101-104">En esta sección se proporcionan ejemplos de programación de LINQ to DataSet en la sintaxis de expresiones de consulta que utilizan los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="9f101-104">This section provides LINQ to DataSet programming examples in query expression syntax that use the standard query operators.</span></span> <span data-ttu-id="9f101-105">El <xref:System.Data.DataSet> usado en estos ejemplos se rellena con el `FillDataSet` método, que se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="9f101-105">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="9f101-106">Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f101-106">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f101-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9f101-107">In This Section</span></span>  

 [<span data-ttu-id="9f101-108">Proyección</span><span class="sxs-lookup"><span data-stu-id="9f101-108">Projection</span></span>](query-expression-syntax-examples-projection-linq-to-dataset.md)  
 <span data-ttu-id="9f101-109">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9f101-109">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="9f101-110">Restricción</span><span class="sxs-lookup"><span data-stu-id="9f101-110">Restriction</span></span>](query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 <span data-ttu-id="9f101-111">Los ejemplos de este tema muestran cómo usar el método <xref:System.Linq.Enumerable.Where%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9f101-111">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="9f101-112">Partitioning</span><span class="sxs-lookup"><span data-stu-id="9f101-112">Partitioning</span></span>](query-expression-syntax-examples-partitioning.md)  
 <span data-ttu-id="9f101-113">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A> para consultar un <xref:System.Data.DataSet> y particionar los resultados.</span><span class="sxs-lookup"><span data-stu-id="9f101-113">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="9f101-114">Ordenación</span><span class="sxs-lookup"><span data-stu-id="9f101-114">Ordering</span></span>](query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="9f101-115">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenByDescending%2A> para consultar un <xref:System.Data.DataSet> y ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="9f101-115">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="9f101-116">Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="9f101-116">Element Operators</span></span>](query-expression-syntax-examples-element-operators.md)  
 <span data-ttu-id="9f101-117">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9f101-117">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="9f101-118">Operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="9f101-118">Aggregate Operators</span></span>](query-expression-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="9f101-119">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar <xref:System.Data.DataSet> y agregar datos.</span><span class="sxs-lookup"><span data-stu-id="9f101-119">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="9f101-120">Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="9f101-120">Join Operators</span></span>](query-expression-syntax-examples-join-operators.md)  
 <span data-ttu-id="9f101-121">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9f101-121">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f101-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f101-122">See also</span></span>

- [<span data-ttu-id="9f101-123">Ejemplos de consultas basadas en métodos</span><span class="sxs-lookup"><span data-stu-id="9f101-123">Method-Based Query Examples</span></span>](method-based-query-examples-linq-to-dataset.md)
- [<span data-ttu-id="9f101-124">Ejemplos de operadores específicos de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="9f101-124">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="9f101-125">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9f101-125">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
