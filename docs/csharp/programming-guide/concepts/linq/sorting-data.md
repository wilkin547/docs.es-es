---
title: Ordenación de datos (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 6a7f687895385bfb77d2a1e3e785742a794bb1b6
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275176"
---
# <a name="sorting-data-c"></a><span data-ttu-id="07cd2-102">Ordenación de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="07cd2-102">Sorting Data (C#)</span></span>
<span data-ttu-id="07cd2-103">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="07cd2-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="07cd2-104">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="07cd2-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="07cd2-105">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="07cd2-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="07cd2-106">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="07cd2-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="07cd2-107">![Operación de ordenación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="07cd2-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="07cd2-108">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07cd2-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="07cd2-109">Methods</span></span>  
  
|<span data-ttu-id="07cd2-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="07cd2-110">Method Name</span></span>|<span data-ttu-id="07cd2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="07cd2-111">Description</span></span>|<span data-ttu-id="07cd2-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="07cd2-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="07cd2-113">Más información</span><span class="sxs-lookup"><span data-stu-id="07cd2-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="07cd2-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="07cd2-114">OrderBy</span></span>|<span data-ttu-id="07cd2-115">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="07cd2-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="07cd2-116">OrderByDescending</span></span>|<span data-ttu-id="07cd2-117">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="07cd2-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="07cd2-118">ThenBy</span></span>|<span data-ttu-id="07cd2-119">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="07cd2-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="07cd2-120">ThenByDescending</span></span>|<span data-ttu-id="07cd2-121">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="07cd2-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="07cd2-122">Reverse</span></span>|<span data-ttu-id="07cd2-123">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="07cd2-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="07cd2-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="07cd2-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="07cd2-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="07cd2-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="07cd2-126">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="07cd2-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="07cd2-127">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="07cd2-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="07cd2-128">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="07cd2-129">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="07cd2-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="07cd2-130">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="07cd2-131">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="07cd2-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="07cd2-132">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="07cd2-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="07cd2-133">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="07cd2-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="07cd2-134">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="07cd2-135">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="07cd2-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="07cd2-136">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="07cd2-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="07cd2-137">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="07cd2-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07cd2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="07cd2-138">See Also</span></span>

- <xref:System.Linq>  
- <span data-ttu-id="07cd2-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="07cd2-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>  
- [<span data-ttu-id="07cd2-140">orderby (cláusula)</span><span class="sxs-lookup"><span data-stu-id="07cd2-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)  
- [<span data-ttu-id="07cd2-141">Cómo: Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="07cd2-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
- [<span data-ttu-id="07cd2-142">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="07cd2-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
