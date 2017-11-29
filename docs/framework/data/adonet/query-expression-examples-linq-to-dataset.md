---
title: Ejemplos de expresiones de consultas (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1967575aa7a287064d6da54d929ce095e89ee24f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="query-expression-examples-linq-to-dataset"></a><span data-ttu-id="c1782-102">Ejemplos de expresiones de consultas (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="c1782-102">Query Expression Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="c1782-103">Esta sección proporciona ejemplos de programación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en la sintaxis de expresión de consultas que usan los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="c1782-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples in query expression syntax that use the standard query operators.</span></span> <span data-ttu-id="c1782-104">El <xref:System.Data.DataSet> usa en estos ejemplos se rellena mediante la `FillDataSet` método, que se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="c1782-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="c1782-105">Para obtener más información, consulte [información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="c1782-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1782-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1782-106">In This Section</span></span>  
 [<span data-ttu-id="c1782-107">Proyección</span><span class="sxs-lookup"><span data-stu-id="c1782-107">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
 <span data-ttu-id="c1782-108">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c1782-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="c1782-109">Restricción</span><span class="sxs-lookup"><span data-stu-id="c1782-109">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 <span data-ttu-id="c1782-110">Los ejemplos de este tema muestran cómo usar el método <xref:System.Linq.Enumerable.Where%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c1782-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="c1782-111">Creación de particiones</span><span class="sxs-lookup"><span data-stu-id="c1782-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
 <span data-ttu-id="c1782-112">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A> para consultar un <xref:System.Data.DataSet> y particionar los resultados.</span><span class="sxs-lookup"><span data-stu-id="c1782-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="c1782-113">Orden</span><span class="sxs-lookup"><span data-stu-id="c1782-113">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="c1782-114">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenByDescending%2A> para consultar un <xref:System.Data.DataSet> y ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="c1782-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="c1782-115">Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="c1782-115">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
 <span data-ttu-id="c1782-116">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c1782-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="c1782-117">Operadores de agregación</span><span class="sxs-lookup"><span data-stu-id="c1782-117">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="c1782-118">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar <xref:System.Data.DataSet> y agregar datos.</span><span class="sxs-lookup"><span data-stu-id="c1782-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="c1782-119">Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="c1782-119">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
 <span data-ttu-id="c1782-120">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c1782-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1782-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1782-121">See Also</span></span>  
 [<span data-ttu-id="c1782-122">Ejemplos de consultas basadas en métodos</span><span class="sxs-lookup"><span data-stu-id="c1782-122">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 [<span data-ttu-id="c1782-123">Ejemplos de operadores específicos del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c1782-123">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [<span data-ttu-id="c1782-124">LINQ to DataSet Examples</span><span class="sxs-lookup"><span data-stu-id="c1782-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
