---
title: Convertir tipos de datos (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: ea1f204ab59ecdd3e3e7e65d12c1be37e9b09f01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736895"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="13b9c-102">Convertir tipos de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="13b9c-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="13b9c-103">Los métodos de conversión cambian el tipo de los objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="13b9c-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="13b9c-104">Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="13b9c-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="13b9c-105">A continuación se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="13b9c-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="13b9c-106">El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="13b9c-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="13b9c-107">El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="13b9c-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="13b9c-108">Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.</span><span class="sxs-lookup"><span data-stu-id="13b9c-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13b9c-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="13b9c-109">Methods</span></span>  
 <span data-ttu-id="13b9c-110">En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="13b9c-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="13b9c-111">Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran.</span><span class="sxs-lookup"><span data-stu-id="13b9c-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="13b9c-112">Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.</span><span class="sxs-lookup"><span data-stu-id="13b9c-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="13b9c-113">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="13b9c-113">Method Name</span></span>|<span data-ttu-id="13b9c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="13b9c-114">Description</span></span>|<span data-ttu-id="13b9c-115">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="13b9c-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="13b9c-116">Más información</span><span class="sxs-lookup"><span data-stu-id="13b9c-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="13b9c-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="13b9c-117">AsEnumerable</span></span>|<span data-ttu-id="13b9c-118">Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="13b9c-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="13b9c-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="13b9c-120">AsQueryable</span></span>|<span data-ttu-id="13b9c-121">Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).</span><span class="sxs-lookup"><span data-stu-id="13b9c-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="13b9c-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-123">Conversión de tipos explícita</span><span class="sxs-lookup"><span data-stu-id="13b9c-123">Cast</span></span>|<span data-ttu-id="13b9c-124">Convierte los elementos de una colección en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="13b9c-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="13b9c-125">Use una variable de rango con tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="13b9c-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="13b9c-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="13b9c-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-127">OfType</span><span class="sxs-lookup"><span data-stu-id="13b9c-127">OfType</span></span>|<span data-ttu-id="13b9c-128">Filtra valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="13b9c-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="13b9c-129">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="13b9c-130">ToArray</span></span>|<span data-ttu-id="13b9c-131">Convierte una colección en una matriz.</span><span class="sxs-lookup"><span data-stu-id="13b9c-131">Converts a collection to an array.</span></span> <span data-ttu-id="13b9c-132">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="13b9c-132">This method forces query execution.</span></span>|<span data-ttu-id="13b9c-133">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="13b9c-134">ToDictionary</span></span>|<span data-ttu-id="13b9c-135">Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="13b9c-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="13b9c-136">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="13b9c-136">This method forces query execution.</span></span>|<span data-ttu-id="13b9c-137">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-138">ToList</span><span class="sxs-lookup"><span data-stu-id="13b9c-138">ToList</span></span>|<span data-ttu-id="13b9c-139">Convierte una colección en <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="13b9c-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="13b9c-140">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="13b9c-140">This method forces query execution.</span></span>|<span data-ttu-id="13b9c-141">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="13b9c-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="13b9c-142">ToLookup</span></span>|<span data-ttu-id="13b9c-143">Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="13b9c-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="13b9c-144">Este método fuerza la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="13b9c-144">This method forces query execution.</span></span>|<span data-ttu-id="13b9c-145">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="13b9c-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="13b9c-146">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="13b9c-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="13b9c-147">En el ejemplo de código siguiente se usa una variable de rango con tipo explícito para convertir un tipo en un subtipo antes de obtener acceso a un miembro que solo está disponible en el subtipo.</span><span class="sxs-lookup"><span data-stu-id="13b9c-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13b9c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="13b9c-148">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="13b9c-149">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="13b9c-149">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="13b9c-150">from (cláusula)</span><span class="sxs-lookup"><span data-stu-id="13b9c-150">from clause</span></span>](../../../../csharp/language-reference/keywords/from-clause.md)
- [<span data-ttu-id="13b9c-151">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="13b9c-151">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="13b9c-152">Cómo: Consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="13b9c-152">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
