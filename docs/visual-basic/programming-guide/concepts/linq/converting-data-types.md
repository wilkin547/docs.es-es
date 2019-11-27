---
title: Convertir tipos de datos
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 25d21954f0bb7555f1f5666f83fb37f4f73e2a60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354252"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="cc21d-102">Convertir tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc21d-102">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="cc21d-103">Los métodos de conversión cambian el tipo de los objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc21d-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="cc21d-104">Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cc21d-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="cc21d-105">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="cc21d-105">The following are some examples:</span></span>

- <span data-ttu-id="cc21d-106">El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="cc21d-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="cc21d-107">El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="cc21d-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="cc21d-108">Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.</span><span class="sxs-lookup"><span data-stu-id="cc21d-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="cc21d-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="cc21d-109">Methods</span></span>

<span data-ttu-id="cc21d-110">En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="cc21d-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="cc21d-111">Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran.</span><span class="sxs-lookup"><span data-stu-id="cc21d-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="cc21d-112">Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cc21d-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="cc21d-113">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="cc21d-113">Method Name</span></span>|<span data-ttu-id="cc21d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc21d-114">Description</span></span>|<span data-ttu-id="cc21d-115">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="cc21d-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="cc21d-116">Más información</span><span class="sxs-lookup"><span data-stu-id="cc21d-116">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="cc21d-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="cc21d-117">AsEnumerable</span></span>|<span data-ttu-id="cc21d-118">Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="cc21d-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="cc21d-119">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="cc21d-120">AsQueryable</span></span>|<span data-ttu-id="cc21d-121">Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).</span><span class="sxs-lookup"><span data-stu-id="cc21d-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="cc21d-122">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-123">Conversión de tipos explícita</span><span class="sxs-lookup"><span data-stu-id="cc21d-123">Cast</span></span>|<span data-ttu-id="cc21d-124">Convierte los elementos de una colección en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="cc21d-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-125">OfType</span><span class="sxs-lookup"><span data-stu-id="cc21d-125">OfType</span></span>|<span data-ttu-id="cc21d-126">Filtra valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="cc21d-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="cc21d-127">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="cc21d-128">ToArray</span></span>|<span data-ttu-id="cc21d-129">Convierte una colección en una matriz.</span><span class="sxs-lookup"><span data-stu-id="cc21d-129">Converts a collection to an array.</span></span> <span data-ttu-id="cc21d-130">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="cc21d-130">This method forces query execution.</span></span>|<span data-ttu-id="cc21d-131">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="cc21d-132">ToDictionary</span></span>|<span data-ttu-id="cc21d-133">Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="cc21d-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="cc21d-134">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="cc21d-134">This method forces query execution.</span></span>|<span data-ttu-id="cc21d-135">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-136">ToList</span><span class="sxs-lookup"><span data-stu-id="cc21d-136">ToList</span></span>|<span data-ttu-id="cc21d-137">Convierte una colección en <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="cc21d-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="cc21d-138">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="cc21d-138">This method forces query execution.</span></span>|<span data-ttu-id="cc21d-139">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="cc21d-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="cc21d-140">ToLookup</span></span>|<span data-ttu-id="cc21d-141">Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="cc21d-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="cc21d-142">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="cc21d-142">This method forces query execution.</span></span>|<span data-ttu-id="cc21d-143">No disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21d-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="cc21d-144">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="cc21d-144">Query Expression Syntax Example</span></span>

<span data-ttu-id="cc21d-145">En el ejemplo de código siguiente se usa la cláusula `From As` para convertir un tipo en un subtipo antes de tener acceso a un miembro que solo está disponible en el subtipo.</span><span class="sxs-lookup"><span data-stu-id="cc21d-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="cc21d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc21d-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="cc21d-147">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc21d-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="cc21d-148">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="cc21d-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="cc21d-149">Cómo: consultar una ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc21d-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
