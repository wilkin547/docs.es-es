---
title: Consultas de agregado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0f76178d6b10e8253fd135c35504389e03d8acae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="aggregate-queries"></a><span data-ttu-id="d8284-102">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="d8284-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d8284-103"> admite los operadores de agregado `Average`, `Count`, `Max`, `Min` y `Sum`.</span><span class="sxs-lookup"><span data-stu-id="d8284-103"> supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="d8284-104">Tener en cuenta las características siguientes de los operadores de agregado en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d8284-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="d8284-105">Las consultas de funciones agregadas se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d8284-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="d8284-106">Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="d8284-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="d8284-107">Las consultas de funciones agregadas normalmente devuelven un número en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="d8284-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="d8284-108">Para obtener más información, consulte [operaciones de agregación](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span><span class="sxs-lookup"><span data-stu-id="d8284-108">For more information, see [Aggregation Operations](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span></span>  
  
-   <span data-ttu-id="d8284-109">No se puede llamar a funciones de agregado en tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="d8284-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="d8284-110">Los ejemplos de los temas siguientes se derivan de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="d8284-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="d8284-111">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d8284-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8284-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d8284-112">In This Section</span></span>  
 [<span data-ttu-id="d8284-113">Devolución del valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d8284-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="d8284-114">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8284-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="d8284-115">Conteo del número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="d8284-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="d8284-116">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8284-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="d8284-117">Búsqueda del valor máximo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d8284-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="d8284-118">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8284-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="d8284-119">Búsqueda del valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d8284-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="d8284-120">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8284-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="d8284-121">Cálculo de la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d8284-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="d8284-122">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8284-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d8284-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d8284-123">Related Sections</span></span>  
 [<span data-ttu-id="d8284-124">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="d8284-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="d8284-125">Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.</span><span class="sxs-lookup"><span data-stu-id="d8284-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="d8284-126">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="d8284-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="d8284-127">Proporciona vínculos a temas donde se explican los conceptos del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8284-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="d8284-128">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d8284-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="d8284-129">Explica cómo funcionan las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8284-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
