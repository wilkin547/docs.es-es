---
title: Consultas de agregado
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: ed8624c47ca8e68646f176ff91b63577d64b6d1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032557"
---
# <a name="aggregate-queries"></a><span data-ttu-id="36c01-102">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="36c01-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="36c01-103">admite los operadores de agregado `Average`, `Count`, `Max`, `Min` y `Sum`.</span><span class="sxs-lookup"><span data-stu-id="36c01-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="36c01-104">Tener en cuenta las características siguientes de los operadores de agregado en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="36c01-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="36c01-105">Las consultas de funciones agregadas se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="36c01-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="36c01-106">Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="36c01-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="36c01-107">Las consultas de funciones agregadas normalmente devuelven un número en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="36c01-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="36c01-108">Para obtener más información, consulte [operaciones de agregación](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="36c01-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="36c01-109">No se puede llamar a funciones de agregado en tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="36c01-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="36c01-110">Los ejemplos de los temas siguientes se derivan de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="36c01-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="36c01-111">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="36c01-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36c01-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36c01-112">In This Section</span></span>  
 [<span data-ttu-id="36c01-113">Devolución del valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="36c01-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="36c01-114">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="36c01-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="36c01-115">Conteo del número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="36c01-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="36c01-116">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="36c01-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="36c01-117">Búsqueda del valor máximo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="36c01-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="36c01-118">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="36c01-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="36c01-119">Búsqueda del valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="36c01-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="36c01-120">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="36c01-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="36c01-121">Cálculo de la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="36c01-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="36c01-122">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="36c01-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="36c01-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="36c01-123">Related Sections</span></span>  
 [<span data-ttu-id="36c01-124">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="36c01-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="36c01-125">Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.</span><span class="sxs-lookup"><span data-stu-id="36c01-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="36c01-126">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="36c01-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="36c01-127">Proporciona vínculos a temas donde se explican los conceptos del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36c01-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="36c01-128">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="36c01-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="36c01-129">Explica cómo funcionan las consultas en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36c01-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
