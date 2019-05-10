---
title: Consultas de agregado
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8a3dd4b80ee8bb09dc0b5a06b6fa603f4b74fdf8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610154"
---
# <a name="aggregate-queries"></a><span data-ttu-id="d3cf3-102">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="d3cf3-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d3cf3-103">admite los operadores de agregado `Average`, `Count`, `Max`, `Min` y `Sum`.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="d3cf3-104">Tener en cuenta las características siguientes de los operadores de agregado en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d3cf3-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="d3cf3-105">Las consultas de funciones agregadas se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="d3cf3-106">Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="d3cf3-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="d3cf3-107">Las consultas de funciones agregadas normalmente devuelven un número en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="d3cf3-108">Para obtener más información, consulte [operaciones de agregación](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="d3cf3-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="d3cf3-109">No se puede llamar a funciones de agregado en tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="d3cf3-110">Los ejemplos de los temas siguientes se derivan de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="d3cf3-111">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d3cf3-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3cf3-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3cf3-112">In This Section</span></span>  
 [<span data-ttu-id="d3cf3-113">Devolución del valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d3cf3-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="d3cf3-114">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="d3cf3-115">Conteo del número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="d3cf3-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="d3cf3-116">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="d3cf3-117">Búsqueda del valor máximo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d3cf3-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="d3cf3-118">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="d3cf3-119">Búsqueda del valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d3cf3-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="d3cf3-120">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="d3cf3-121">Cálculo de la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="d3cf3-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="d3cf3-122">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3cf3-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d3cf3-123">Related Sections</span></span>  
 [<span data-ttu-id="d3cf3-124">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="d3cf3-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="d3cf3-125">Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.</span><span class="sxs-lookup"><span data-stu-id="d3cf3-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="d3cf3-126">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="d3cf3-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="d3cf3-127">Proporciona vínculos a temas donde se explican los conceptos del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cf3-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="d3cf3-128">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d3cf3-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="d3cf3-129">Explica cómo funcionan las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3cf3-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
