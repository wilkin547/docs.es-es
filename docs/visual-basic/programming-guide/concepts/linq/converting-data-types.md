---
description: Más información acerca de la conversión de tipos de datos (Visual Basic)
title: Convertir tipos de datos
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 7650f5d5d6f727b7815b9dd2de8a565e27fa18d9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428719"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="58953-103">Convertir tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58953-103">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="58953-104">Los métodos de conversión cambian el tipo de los objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="58953-104">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="58953-105">Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="58953-105">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="58953-106">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="58953-106">The following are some examples:</span></span>

- <span data-ttu-id="58953-107">El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="58953-107">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="58953-108">El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="58953-108">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="58953-109">Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.</span><span class="sxs-lookup"><span data-stu-id="58953-109">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="58953-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="58953-110">Methods</span></span>

<span data-ttu-id="58953-111">En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="58953-111">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="58953-112">Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran.</span><span class="sxs-lookup"><span data-stu-id="58953-112">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="58953-113">Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.</span><span class="sxs-lookup"><span data-stu-id="58953-113">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="58953-114">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="58953-114">Method Name</span></span>|<span data-ttu-id="58953-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="58953-115">Description</span></span>|<span data-ttu-id="58953-116">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="58953-116">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="58953-117">Más información</span><span class="sxs-lookup"><span data-stu-id="58953-117">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="58953-118">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="58953-118">AsEnumerable</span></span>|<span data-ttu-id="58953-119">Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="58953-119">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="58953-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="58953-121">AsQueryable</span></span>|<span data-ttu-id="58953-122">Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).</span><span class="sxs-lookup"><span data-stu-id="58953-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="58953-123">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-123">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-124">Conversión de tipos explícita</span><span class="sxs-lookup"><span data-stu-id="58953-124">Cast</span></span>|<span data-ttu-id="58953-125">Convierte los elementos de una colección en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="58953-125">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-126">OfType</span><span class="sxs-lookup"><span data-stu-id="58953-126">OfType</span></span>|<span data-ttu-id="58953-127">Filtra valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="58953-127">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="58953-128">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-129">ToArray</span><span class="sxs-lookup"><span data-stu-id="58953-129">ToArray</span></span>|<span data-ttu-id="58953-130">Convierte una colección en una matriz.</span><span class="sxs-lookup"><span data-stu-id="58953-130">Converts a collection to an array.</span></span> <span data-ttu-id="58953-131">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="58953-131">This method forces query execution.</span></span>|<span data-ttu-id="58953-132">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-133">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="58953-133">ToDictionary</span></span>|<span data-ttu-id="58953-134">Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="58953-134">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="58953-135">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="58953-135">This method forces query execution.</span></span>|<span data-ttu-id="58953-136">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-137">ToList</span><span class="sxs-lookup"><span data-stu-id="58953-137">ToList</span></span>|<span data-ttu-id="58953-138">Convierte una colección en <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="58953-138">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="58953-139">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="58953-139">This method forces query execution.</span></span>|<span data-ttu-id="58953-140">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-140">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="58953-141">ToLookup</span><span class="sxs-lookup"><span data-stu-id="58953-141">ToLookup</span></span>|<span data-ttu-id="58953-142">Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="58953-142">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="58953-143">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="58953-143">This method forces query execution.</span></span>|<span data-ttu-id="58953-144">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="58953-144">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="58953-145">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="58953-145">Query Expression Syntax Example</span></span>

<span data-ttu-id="58953-146">En el ejemplo de código siguiente `From As` se usa la cláusula para convertir un tipo en un subtipo antes de tener acceso a un miembro que solo está disponible en el subtipo.</span><span class="sxs-lookup"><span data-stu-id="58953-146">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58953-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58953-147">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="58953-148">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58953-148">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="58953-149">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="58953-149">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="58953-150">Cómo: consultar una ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58953-150">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](how-to-query-an-arraylist-with-linq.md)
