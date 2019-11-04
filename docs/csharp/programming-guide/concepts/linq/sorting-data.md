---
title: Ordenación de datos (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 78b263c384895b736b11cc524befa42b4a896380
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418186"
---
# <a name="sorting-data-c"></a><span data-ttu-id="96807-102">Ordenación de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="96807-102">Sorting Data (C#)</span></span>
<span data-ttu-id="96807-103">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="96807-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="96807-104">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="96807-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="96807-105">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="96807-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="96807-106">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="96807-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span> 
  
 ![Gráfico que muestra una operación de ordenación alfabética.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="96807-108">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="96807-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96807-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="96807-109">Methods</span></span>  
  
|<span data-ttu-id="96807-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="96807-110">Method Name</span></span>|<span data-ttu-id="96807-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="96807-111">Description</span></span>|<span data-ttu-id="96807-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="96807-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="96807-113">Más información</span><span class="sxs-lookup"><span data-stu-id="96807-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="96807-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="96807-114">OrderBy</span></span>|<span data-ttu-id="96807-115">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="96807-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="96807-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="96807-116">OrderByDescending</span></span>|<span data-ttu-id="96807-117">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="96807-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="96807-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="96807-118">ThenBy</span></span>|<span data-ttu-id="96807-119">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="96807-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="96807-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="96807-120">ThenByDescending</span></span>|<span data-ttu-id="96807-121">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="96807-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="96807-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="96807-122">Reverse</span></span>|<span data-ttu-id="96807-123">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="96807-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="96807-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="96807-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="96807-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="96807-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="96807-126">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="96807-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="96807-127">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="96807-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="96807-128">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="96807-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="96807-129">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="96807-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="96807-130">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="96807-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="96807-131">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="96807-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="96807-132">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="96807-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="96807-133">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="96807-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="96807-134">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="96807-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="96807-135">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="96807-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="96807-136">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="96807-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="96807-137">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="96807-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="96807-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="96807-138">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="96807-139">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="96807-139">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="96807-140">orderby (cláusula)</span><span class="sxs-lookup"><span data-stu-id="96807-140">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="96807-141">Cómo: Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="96807-141">How to: Order the Results of a Join Clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="96807-142">Cómo: Ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="96807-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
