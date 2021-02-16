---
description: Más información acerca de la ordenación de datos (Visual Basic)
title: Ordenación de datos
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: 83e05b2af1b3421d004a87630cd5df43f2a21ae4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468556"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="c82cb-103">Ordenar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c82cb-103">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="c82cb-104">Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="c82cb-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="c82cb-105">El primer criterio de ordenación realiza una ordenación primaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="c82cb-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="c82cb-106">Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.</span><span class="sxs-lookup"><span data-stu-id="c82cb-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="c82cb-107">En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c82cb-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![Gráfico que muestra una operación de ordenación alfabética.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="c82cb-109">Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-109">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="c82cb-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="c82cb-110">Methods</span></span>

|<span data-ttu-id="c82cb-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="c82cb-111">Method Name</span></span>|<span data-ttu-id="c82cb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82cb-112">Description</span></span>|<span data-ttu-id="c82cb-113">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="c82cb-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c82cb-114">Más información</span><span class="sxs-lookup"><span data-stu-id="c82cb-114">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="c82cb-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="c82cb-115">OrderBy</span></span>|<span data-ttu-id="c82cb-116">Ordena valores en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-116">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="c82cb-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="c82cb-117">OrderByDescending</span></span>|<span data-ttu-id="c82cb-118">Ordena valores en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-118">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="c82cb-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="c82cb-119">ThenBy</span></span>|<span data-ttu-id="c82cb-120">Realiza una ordenación secundaria en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-120">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="c82cb-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="c82cb-121">ThenByDescending</span></span>|<span data-ttu-id="c82cb-122">Realiza una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-122">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="c82cb-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="c82cb-123">Reverse</span></span>|<span data-ttu-id="c82cb-124">Invierte el orden de los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="c82cb-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="c82cb-125">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="c82cb-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c82cb-126">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="c82cb-126">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="c82cb-127">Ejemplos de ordenación principal</span><span class="sxs-lookup"><span data-stu-id="c82cb-127">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="c82cb-128">Orden ascendente principal</span><span class="sxs-lookup"><span data-stu-id="c82cb-128">Primary Ascending Sort</span></span>

<span data-ttu-id="c82cb-129">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-129">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

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

#### <a name="primary-descending-sort"></a><span data-ttu-id="c82cb-130">Orden descendente principal</span><span class="sxs-lookup"><span data-stu-id="c82cb-130">Primary Descending Sort</span></span>

<span data-ttu-id="c82cb-131">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-131">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

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

### <a name="secondary-sort-examples"></a><span data-ttu-id="c82cb-132">Ejemplos de ordenación secundaria</span><span class="sxs-lookup"><span data-stu-id="c82cb-132">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="c82cb-133">Orden ascendente secundario</span><span class="sxs-lookup"><span data-stu-id="c82cb-133">Secondary Ascending Sort</span></span>

<span data-ttu-id="c82cb-134">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz.</span><span class="sxs-lookup"><span data-stu-id="c82cb-134">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="c82cb-135">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

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

#### <a name="secondary-descending-sort"></a><span data-ttu-id="c82cb-136">Orden descendente secundario</span><span class="sxs-lookup"><span data-stu-id="c82cb-136">Secondary Descending Sort</span></span>

<span data-ttu-id="c82cb-137">En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="c82cb-137">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="c82cb-138">Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.</span><span class="sxs-lookup"><span data-stu-id="c82cb-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c82cb-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c82cb-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c82cb-140">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c82cb-140">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="c82cb-141">Cláusula order by</span><span class="sxs-lookup"><span data-stu-id="c82cb-141">Order By Clause</span></span>](../../../language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="c82cb-142">Cómo: Ordenar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="c82cb-142">How to: Sort Query Results</span></span>](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="c82cb-143">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c82cb-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
