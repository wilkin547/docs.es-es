---
title: "Operaciones de agregación (C#)"
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
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
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
ms.openlocfilehash: 6c453bdccdb3af026fe4f4fb79c6e33e44e7a8f0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="aggregation-operations-c"></a><span data-ttu-id="3b3ba-102">Operaciones de agregación (C#)</span><span class="sxs-lookup"><span data-stu-id="3b3ba-102">Aggregation Operations (C#)</span></span>
<span data-ttu-id="3b3ba-103">Una operación de agregación calcula un valor único a partir de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="3b3ba-104">Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="3b3ba-105">En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="3b3ba-106">La primera operación suma los números.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-106">The first operation sums the numbers.</span></span> <span data-ttu-id="3b3ba-107">La segunda operación devuelve el valor máximo de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="3b3ba-108">![Operaciones de agregación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="3b3ba-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="3b3ba-109">Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b3ba-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="3b3ba-110">Methods</span></span>  
  
|<span data-ttu-id="3b3ba-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="3b3ba-111">Method Name</span></span>|<span data-ttu-id="3b3ba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b3ba-112">Description</span></span>|<span data-ttu-id="3b3ba-113">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="3b3ba-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="3b3ba-114">Más información</span><span class="sxs-lookup"><span data-stu-id="3b3ba-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="3b3ba-115">Agregar</span><span class="sxs-lookup"><span data-stu-id="3b3ba-115">Aggregate</span></span>|<span data-ttu-id="3b3ba-116">Realiza una operación de agregación personalizada en los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="3b3ba-117">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-118">Average</span><span class="sxs-lookup"><span data-stu-id="3b3ba-118">Average</span></span>|<span data-ttu-id="3b3ba-119">Calcula el valor medio de una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-119">Calculates the average value of a collection of values.</span></span>|<span data-ttu-id="3b3ba-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-121">Recuento</span><span class="sxs-lookup"><span data-stu-id="3b3ba-121">Count</span></span>|<span data-ttu-id="3b3ba-122">Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="3b3ba-123">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="3b3ba-124">LongCount</span></span>|<span data-ttu-id="3b3ba-125">Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-125">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="3b3ba-126">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-127">Máx.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-127">Max</span></span>|<span data-ttu-id="3b3ba-128">Determina el valor máximo de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-128">Determines the maximum value in a collection.</span></span>|<span data-ttu-id="3b3ba-129">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-130">Mín.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-130">Min</span></span>|<span data-ttu-id="3b3ba-131">Determina el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-131">Determines the minimum value in a collection.</span></span>|<span data-ttu-id="3b3ba-132">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|<span data-ttu-id="3b3ba-133">Sum</span><span class="sxs-lookup"><span data-stu-id="3b3ba-133">Sum</span></span>|<span data-ttu-id="3b3ba-134">Calcula la suma de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-134">Calculates the sum of the values in a collection.</span></span>|<span data-ttu-id="3b3ba-135">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3b3ba-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="3b3ba-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b3ba-136">See Also</span></span>  
 <span data-ttu-id="3b3ba-137"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="3b3ba-137"><xref:System.Linq></span></span>   
 <span data-ttu-id="3b3ba-138">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="3b3ba-138">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="3b3ba-139">[Cómo: Calcular valores de columna en un archivo de texto CSV (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span><span class="sxs-lookup"><span data-stu-id="3b3ba-139">[How to: Compute Column Values in a CSV Text File (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span></span>  
 <span data-ttu-id="3b3ba-140">[Cómo: Buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span><span class="sxs-lookup"><span data-stu-id="3b3ba-140">[How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span></span>  
 [<span data-ttu-id="3b3ba-141">Cómo: Buscar el número total de bytes en un conjunto de carpetas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3b3ba-141">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)

