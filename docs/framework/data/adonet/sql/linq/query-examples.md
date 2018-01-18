---
title: Ejemplos de consultas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a><span data-ttu-id="7cacb-102">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="7cacb-102">Query Examples</span></span>
<span data-ttu-id="7cacb-103">En esta sección se proporcionan ejemplos de consultas [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] típicas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y C#.</span><span class="sxs-lookup"><span data-stu-id="7cacb-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="7cacb-104">Los programadores que utilicen [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] encontrarán muchos más ejemplos en la solución de ejemplo que está disponible en la sección Ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7cacb-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="7cacb-105">Para obtener más información, consulte [ejemplos](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="7cacb-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7cacb-106">*base de datos* a menudo se utiliza en los ejemplos de código de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación.</span><span class="sxs-lookup"><span data-stu-id="7cacb-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="7cacb-107">*base de datos* se supone que es una instancia de un *Northwind* (clase), que se hereda de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7cacb-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7cacb-108">In This Section</span></span>  
 [<span data-ttu-id="7cacb-109">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="7cacb-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="7cacb-110">Describe cómo utilizar <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, etc.</span><span class="sxs-lookup"><span data-stu-id="7cacb-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="7cacb-111">Devolución del primer elemento de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7cacb-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="7cacb-112">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-113">Devolución u omisión de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7cacb-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="7cacb-114">Proporciona ejemplos de cómo se utilizan <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-115">Ordenación de los elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7cacb-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="7cacb-116">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-117">Agrupación de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7cacb-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="7cacb-118">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-119">Eliminación de elementos duplicados de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7cacb-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="7cacb-120">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-121">Determinación de si alguno o todos los elementos de una secuencia satisfacen una condición</span><span class="sxs-lookup"><span data-stu-id="7cacb-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="7cacb-122">Proporciona ejemplos de cómo se utilizan <xref:System.Linq.Enumerable.All%2A> y <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-123">Concatenación de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="7cacb-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="7cacb-124">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-125">Devolución de la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="7cacb-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="7cacb-126">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-127">Devolución de la intersección de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="7cacb-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="7cacb-128">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-129">Devolución de la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="7cacb-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="7cacb-130">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-131">Conversión de una secuencia en una matriz</span><span class="sxs-lookup"><span data-stu-id="7cacb-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="7cacb-132">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-133">Conversión de una secuencia en una lista genérica</span><span class="sxs-lookup"><span data-stu-id="7cacb-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="7cacb-134">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-135">Conversión de un tipo en una interfaz IEnumerable genérica</span><span class="sxs-lookup"><span data-stu-id="7cacb-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="7cacb-136">Proporciona ejemplos de cómo se utiliza <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cacb-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="7cacb-137">Formulación de combinaciones y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="7cacb-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="7cacb-138">Proporciona ejemplos de cómo se utiliza la navegación de clave externa en las cláusulas `from`, `where` y `select`.</span><span class="sxs-lookup"><span data-stu-id="7cacb-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="7cacb-139">Formulación de proyecciones</span><span class="sxs-lookup"><span data-stu-id="7cacb-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="7cacb-140">Proporciona ejemplos de cómo combinar `select` con otras características (por ejemplo, *tipos anónimos*) para formar proyecciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="7cacb-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7cacb-141">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7cacb-141">Related Sections</span></span>  
 [<span data-ttu-id="7cacb-142">Información general sobre operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="7cacb-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="7cacb-143">Explica el concepto de operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="7cacb-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="7cacb-144">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="7cacb-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="7cacb-145">Explica cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza conceptos que se aplican a las consultas.</span><span class="sxs-lookup"><span data-stu-id="7cacb-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="7cacb-146">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="7cacb-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="7cacb-147">Proporciona un portal de temas que explican conceptos de programación relacionados con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cacb-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
