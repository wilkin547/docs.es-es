---
description: 'Más información sobre: consultas de agregado'
title: Consultas de agregado
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 2b9b71440c804740e2f04d5b2dc8c2cd111634b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712836"
---
# <a name="aggregate-queries"></a><span data-ttu-id="bea6e-103">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="bea6e-103">Aggregate Queries</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="bea6e-104">admite los operadores de agregado `Average`, `Count`, `Max`, `Min` y `Sum`.</span><span class="sxs-lookup"><span data-stu-id="bea6e-104">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="bea6e-105">Tener en cuenta las características siguientes de los operadores de agregado en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bea6e-105">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="bea6e-106">Las consultas de funciones agregadas se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="bea6e-106">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="bea6e-107">Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bea6e-107">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="bea6e-108">Las consultas de funciones agregadas normalmente devuelven un número en lugar de una colección.</span><span class="sxs-lookup"><span data-stu-id="bea6e-108">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="bea6e-109">Para obtener más información, vea [operaciones de agregación](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="bea6e-109">For more information, see [Aggregation Operations](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="bea6e-110">No se puede llamar a funciones de agregado en tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="bea6e-110">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="bea6e-111">Los ejemplos de los temas siguientes se derivan de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bea6e-111">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="bea6e-112">Para obtener más información, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="bea6e-112">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bea6e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bea6e-113">In This Section</span></span>  

 [<span data-ttu-id="bea6e-114">Devolver el valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="bea6e-114">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="bea6e-115">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="bea6e-115">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="bea6e-116">Contar el número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="bea6e-116">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="bea6e-117">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="bea6e-117">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="bea6e-118">Buscar el valor máximo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="bea6e-118">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="bea6e-119">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="bea6e-119">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="bea6e-120">Buscar el valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="bea6e-120">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="bea6e-121">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="bea6e-121">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="bea6e-122">Calcular la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="bea6e-122">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="bea6e-123">Muestra cómo utilizar el operador <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="bea6e-123">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bea6e-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bea6e-124">Related Sections</span></span>  

 [<span data-ttu-id="bea6e-125">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="bea6e-125">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="bea6e-126">Proporciona vínculos a consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en Visual Basic y C#.</span><span class="sxs-lookup"><span data-stu-id="bea6e-126">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="bea6e-127">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="bea6e-127">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="bea6e-128">Proporciona vínculos a temas que explican los conceptos para diseñar consultas LINQ en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bea6e-128">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="bea6e-129">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="bea6e-129">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="bea6e-130">Explica cómo funcionan las consultas en LINQ.</span><span class="sxs-lookup"><span data-stu-id="bea6e-130">Explains how queries work in LINQ.</span></span>
