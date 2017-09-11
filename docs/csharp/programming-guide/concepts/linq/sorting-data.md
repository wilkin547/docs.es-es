---
title: "Ordenación de datos (C#)"
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
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
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
ms.openlocfilehash: ff6ef81486074f2e738b62ce37e6cb58bff49bf8
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="sorting-data-c"></a><span data-ttu-id="6a5b5-102">Ordenación de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="6a5b5-102">Sorting Data (C#)</span></span>
<span data-ttu-id="6a5b5-103">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="6a5b5-104">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="6a5b5-105">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="6a5b5-106">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="6a5b5-107">![Operación de ordenación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="6a5b5-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="6a5b5-108">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a5b5-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="6a5b5-109">Methods</span></span>  
  
|<span data-ttu-id="6a5b5-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="6a5b5-110">Method Name</span></span>|<span data-ttu-id="6a5b5-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a5b5-111">Description</span></span>|<span data-ttu-id="6a5b5-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="6a5b5-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="6a5b5-113">Más información</span><span class="sxs-lookup"><span data-stu-id="6a5b5-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="6a5b5-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="6a5b5-114">OrderBy</span></span>|<span data-ttu-id="6a5b5-115">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="6a5b5-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="6a5b5-116">OrderByDescending</span></span>|<span data-ttu-id="6a5b5-117">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="6a5b5-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="6a5b5-118">ThenBy</span></span>|<span data-ttu-id="6a5b5-119">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="6a5b5-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="6a5b5-120">ThenByDescending</span></span>|<span data-ttu-id="6a5b5-121">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="6a5b5-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="6a5b5-122">Reverse</span></span>|<span data-ttu-id="6a5b5-123">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="6a5b5-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="6a5b5-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="6a5b5-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="6a5b5-126">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="6a5b5-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="6a5b5-127">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="6a5b5-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="6a5b5-128">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="6a5b5-129">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="6a5b5-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="6a5b5-130">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby``descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="6a5b5-131">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="6a5b5-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="6a5b5-132">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="6a5b5-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="6a5b5-133">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="6a5b5-134">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="6a5b5-135">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="6a5b5-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="6a5b5-136">En el siguiente ejemplo se muestra cómo usar la cláusula `orderby``descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="6a5b5-137">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="6a5b5-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a5b5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a5b5-138">See Also</span></span>  
 <span data-ttu-id="6a5b5-139"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="6a5b5-139"><xref:System.Linq></span></span>   
 <span data-ttu-id="6a5b5-140">[Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="6a5b5-140">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="6a5b5-141">[orderby (Cláusula)](../../../../csharp/language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="6a5b5-141">[orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md) </span></span>  
 <span data-ttu-id="6a5b5-142">[Cómo: Ordenar los resultados de una cláusula join](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="6a5b5-142">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 [<span data-ttu-id="6a5b5-143">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6a5b5-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

