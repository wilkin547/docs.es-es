---
title: Ordenar datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: f52000d37df45c97754463de1e81cd523806e9c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646869"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="42b1b-102">Ordenar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42b1b-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="42b1b-103">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="42b1b-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="42b1b-104">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="42b1b-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="42b1b-105">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="42b1b-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="42b1b-106">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="42b1b-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="42b1b-107">![Operación de ordenación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="42b1b-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="42b1b-108">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42b1b-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="42b1b-109">Methods</span></span>  
  
|<span data-ttu-id="42b1b-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="42b1b-110">Method Name</span></span>|<span data-ttu-id="42b1b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="42b1b-111">Description</span></span>|<span data-ttu-id="42b1b-112">Sintaxis de expresiones de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42b1b-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="42b1b-113">Más información</span><span class="sxs-lookup"><span data-stu-id="42b1b-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="42b1b-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="42b1b-114">OrderBy</span></span>|<span data-ttu-id="42b1b-115">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42b1b-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="42b1b-116">OrderByDescending</span></span>|<span data-ttu-id="42b1b-117">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42b1b-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="42b1b-118">ThenBy</span></span>|<span data-ttu-id="42b1b-119">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42b1b-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="42b1b-120">ThenByDescending</span></span>|<span data-ttu-id="42b1b-121">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42b1b-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="42b1b-122">Reverse</span></span>|<span data-ttu-id="42b1b-123">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="42b1b-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="42b1b-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="42b1b-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="42b1b-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="42b1b-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="42b1b-126">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="42b1b-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="42b1b-127">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="42b1b-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="42b1b-128">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="42b1b-129">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="42b1b-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="42b1b-130">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="42b1b-131">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="42b1b-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="42b1b-132">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="42b1b-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="42b1b-133">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="42b1b-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="42b1b-134">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="42b1b-135">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="42b1b-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="42b1b-136">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="42b1b-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="42b1b-137">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="42b1b-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="42b1b-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="42b1b-138">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="42b1b-139">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42b1b-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="42b1b-140">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="42b1b-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="42b1b-141">Cómo: Ordenar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="42b1b-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)  
 [<span data-ttu-id="42b1b-142">Cómo: ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42b1b-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
