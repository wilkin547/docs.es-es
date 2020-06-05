---
title: Ordenación de datos
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: a5ccff745995ed7f41731cf98fb7c49d3247d994
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406799"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="3177a-102">Ordenar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3177a-102">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="3177a-103">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="3177a-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="3177a-104">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="3177a-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="3177a-105">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="3177a-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="3177a-106">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3177a-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![Gráfico que muestra una operación de ordenación alfabética.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="3177a-108">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3177a-108">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="3177a-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="3177a-109">Methods</span></span>

|<span data-ttu-id="3177a-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="3177a-110">Method Name</span></span>|<span data-ttu-id="3177a-111">Description</span><span class="sxs-lookup"><span data-stu-id="3177a-111">Description</span></span>|<span data-ttu-id="3177a-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3177a-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3177a-113">Más información</span><span class="sxs-lookup"><span data-stu-id="3177a-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="3177a-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="3177a-114">OrderBy</span></span>|<span data-ttu-id="3177a-115">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="3177a-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="3177a-116">OrderByDescending</span></span>|<span data-ttu-id="3177a-117">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="3177a-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="3177a-118">ThenBy</span></span>|<span data-ttu-id="3177a-119">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="3177a-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="3177a-120">ThenByDescending</span></span>|<span data-ttu-id="3177a-121">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="3177a-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="3177a-122">Reverse</span></span>|<span data-ttu-id="3177a-123">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="3177a-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="3177a-124">No disponible.</span><span class="sxs-lookup"><span data-stu-id="3177a-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="3177a-125">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3177a-125">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="3177a-126">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="3177a-126">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="3177a-127">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="3177a-127">Primary Ascending Sort</span></span>

<span data-ttu-id="3177a-128">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

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

#### <a name="primary-descending-sort"></a><span data-ttu-id="3177a-129">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="3177a-129">Primary Descending Sort</span></span>

<span data-ttu-id="3177a-130">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

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

### <a name="secondary-sort-examples"></a><span data-ttu-id="3177a-131">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="3177a-131">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="3177a-132">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="3177a-132">Secondary Ascending Sort</span></span>

<span data-ttu-id="3177a-133">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="3177a-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="3177a-134">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

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

#### <a name="secondary-descending-sort"></a><span data-ttu-id="3177a-135">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="3177a-135">Secondary Descending Sort</span></span>

<span data-ttu-id="3177a-136">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="3177a-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="3177a-137">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3177a-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3177a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3177a-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3177a-139">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3177a-139">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="3177a-140">Cláusula Order By</span><span class="sxs-lookup"><span data-stu-id="3177a-140">Order By Clause</span></span>](../../../language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="3177a-141">Cómo: Ordenar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="3177a-141">How to: Sort Query Results</span></span>](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="3177a-142">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3177a-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
