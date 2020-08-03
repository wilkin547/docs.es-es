---
title: Convertir tipos de datos (C#)
description: Los métodos de conversión cambian el tipo de los objetos de entrada. Vea operaciones de conversión en consultas de LINQ en C#, como Enumerable.AsEnumerable y Enumerable.OfType.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 3291690f9aaee945ca7feb04ebbc676db2612894
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105493"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="71267-104">Convertir tipos de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="71267-104">Converting Data Types (C#)</span></span>
<span data-ttu-id="71267-105">Los métodos de conversión cambian el tipo de los objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="71267-105">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="71267-106">Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="71267-106">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="71267-107">A continuación se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="71267-107">Following are some examples:</span></span>

- <span data-ttu-id="71267-108">El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="71267-108">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="71267-109">El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="71267-109">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="71267-110">Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.</span><span class="sxs-lookup"><span data-stu-id="71267-110">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="71267-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="71267-111">Methods</span></span>
 <span data-ttu-id="71267-112">En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="71267-112">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="71267-113">Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran.</span><span class="sxs-lookup"><span data-stu-id="71267-113">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="71267-114">Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.</span><span class="sxs-lookup"><span data-stu-id="71267-114">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="71267-115">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="71267-115">Method Name</span></span>|<span data-ttu-id="71267-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="71267-116">Description</span></span>|<span data-ttu-id="71267-117">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="71267-117">C# Query Expression Syntax</span></span>|<span data-ttu-id="71267-118">Más información</span><span class="sxs-lookup"><span data-stu-id="71267-118">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="71267-119">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="71267-119">AsEnumerable</span></span>|<span data-ttu-id="71267-120">Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="71267-120">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="71267-121">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-122">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="71267-122">AsQueryable</span></span>|<span data-ttu-id="71267-123">Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).</span><span class="sxs-lookup"><span data-stu-id="71267-123">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="71267-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-124">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-125">Conversión de tipos explícita</span><span class="sxs-lookup"><span data-stu-id="71267-125">Cast</span></span>|<span data-ttu-id="71267-126">Convierte los elementos de una colección en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="71267-126">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="71267-127">Use una variable de rango con tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="71267-127">Use an explicitly typed range variable.</span></span> <span data-ttu-id="71267-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71267-128">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-129">OfType</span><span class="sxs-lookup"><span data-stu-id="71267-129">OfType</span></span>|<span data-ttu-id="71267-130">Filtra valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="71267-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="71267-131">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-132">ToArray</span><span class="sxs-lookup"><span data-stu-id="71267-132">ToArray</span></span>|<span data-ttu-id="71267-133">Convierte una colección en una matriz.</span><span class="sxs-lookup"><span data-stu-id="71267-133">Converts a collection to an array.</span></span> <span data-ttu-id="71267-134">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="71267-134">This method forces query execution.</span></span>|<span data-ttu-id="71267-135">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-136">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="71267-136">ToDictionary</span></span>|<span data-ttu-id="71267-137">Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="71267-137">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="71267-138">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="71267-138">This method forces query execution.</span></span>|<span data-ttu-id="71267-139">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-140">ToList</span><span class="sxs-lookup"><span data-stu-id="71267-140">ToList</span></span>|<span data-ttu-id="71267-141">Convierte una colección en <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="71267-141">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="71267-142">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="71267-142">This method forces query execution.</span></span>|<span data-ttu-id="71267-143">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="71267-144">ToLookup</span><span class="sxs-lookup"><span data-stu-id="71267-144">ToLookup</span></span>|<span data-ttu-id="71267-145">Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="71267-145">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="71267-146">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="71267-146">This method forces query execution.</span></span>|<span data-ttu-id="71267-147">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="71267-147">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="71267-148">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="71267-148">Query Expression Syntax Example</span></span>

<span data-ttu-id="71267-149">En el ejemplo de código siguiente se usa una variable de rango con tipo explícito para convertir un tipo en un subtipo antes de obtener acceso a un miembro que solo está disponible en el subtipo.</span><span class="sxs-lookup"><span data-stu-id="71267-149">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a><span data-ttu-id="71267-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71267-150">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="71267-151">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="71267-151">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="71267-152">from (cláusula)</span><span class="sxs-lookup"><span data-stu-id="71267-152">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="71267-153">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="71267-153">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="71267-154">Procedimiento para consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="71267-154">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
