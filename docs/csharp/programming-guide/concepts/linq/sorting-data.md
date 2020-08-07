---
title: Ordenación de datos (C#)
description: Aprenda sobre las operaciones de ordenación y los métodos de operador de consulta estándar que realizan operaciones de ordenación en LINQ en C#.
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 5feeb0e2229fc370fdcb9608817f41832bffd7cc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302339"
---
# <a name="sorting-data-c"></a><span data-ttu-id="e21a6-103">Ordenación de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="e21a6-103">Sorting Data (C#)</span></span>
<span data-ttu-id="e21a6-104">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="e21a6-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="e21a6-105">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="e21a6-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="e21a6-106">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="e21a6-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="e21a6-107">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="e21a6-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![Gráfico que muestra una operación de ordenación alfabética.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="e21a6-109">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-109">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e21a6-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="e21a6-110">Methods</span></span>  
  
|<span data-ttu-id="e21a6-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="e21a6-111">Method Name</span></span>|<span data-ttu-id="e21a6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e21a6-112">Description</span></span>|<span data-ttu-id="e21a6-113">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="e21a6-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="e21a6-114">Más información</span><span class="sxs-lookup"><span data-stu-id="e21a6-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e21a6-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="e21a6-115">OrderBy</span></span>|<span data-ttu-id="e21a6-116">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-116">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e21a6-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="e21a6-117">OrderByDescending</span></span>|<span data-ttu-id="e21a6-118">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-118">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e21a6-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="e21a6-119">ThenBy</span></span>|<span data-ttu-id="e21a6-120">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-120">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e21a6-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="e21a6-121">ThenByDescending</span></span>|<span data-ttu-id="e21a6-122">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-122">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e21a6-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="e21a6-123">Reverse</span></span>|<span data-ttu-id="e21a6-124">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="e21a6-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="e21a6-125">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e21a6-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e21a6-126">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="e21a6-126">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="e21a6-127">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="e21a6-127">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="e21a6-128">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="e21a6-128">Primary Ascending Sort</span></span>  
 <span data-ttu-id="e21a6-129">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-129">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="e21a6-130">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="e21a6-130">Primary Descending Sort</span></span>  
 <span data-ttu-id="e21a6-131">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-131">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="e21a6-132">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="e21a6-132">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="e21a6-133">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="e21a6-133">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="e21a6-134">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e21a6-134">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="e21a6-135">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="e21a6-136">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="e21a6-136">Secondary Descending Sort</span></span>  
 <span data-ttu-id="e21a6-137">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="e21a6-137">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="e21a6-138">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="e21a6-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="e21a6-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e21a6-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e21a6-140">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="e21a6-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="e21a6-141">orderby (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e21a6-141">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="e21a6-142">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="e21a6-142">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="e21a6-143">Procedimiento para ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e21a6-143">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
