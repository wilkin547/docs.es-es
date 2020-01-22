---
title: Colecciones (C#)
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: 23d73a26bbe0e711bb3a081994826e06634c4bac
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418706"
---
# <a name="collections-c"></a><span data-ttu-id="a76bc-102">Colecciones (C#)</span><span class="sxs-lookup"><span data-stu-id="a76bc-102">Collections (C#)</span></span>

<span data-ttu-id="a76bc-103">Para muchas aplicaciones, puede que desee crear y administrar grupos de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="a76bc-104">Existen dos formas de agrupar objetos: mediante la creación de matrices de objetos y con la creación de colecciones de objetos.</span><span class="sxs-lookup"><span data-stu-id="a76bc-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>

<span data-ttu-id="a76bc-105">Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="a76bc-106">Para obtener información sobre las matrices, vea [Matrices](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-106">For information about arrays, see [Arrays](../arrays/index.md).</span></span>

<span data-ttu-id="a76bc-107">Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos.</span><span class="sxs-lookup"><span data-stu-id="a76bc-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="a76bc-108">A diferencia de las matrices, el grupo de objetos con el que trabaja puede aumentar y reducirse de manera dinámica a medida que cambian las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a76bc-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="a76bc-109">Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.</span><span class="sxs-lookup"><span data-stu-id="a76bc-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>

<span data-ttu-id="a76bc-110">Una colección es una clase, por lo que debe declarar una instancia de la clase para poder agregar elementos a dicha colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>

<span data-ttu-id="a76bc-111">Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a76bc-112">Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="a76bc-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="a76bc-113">Cuando recupera un elemento de una colección genérica, no tiene que determinar su tipo de datos ni convertirlo.</span><span class="sxs-lookup"><span data-stu-id="a76bc-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>

> [!NOTE]
> <span data-ttu-id="a76bc-114">Para los ejemplos de este tema, incluya las directivas [using](../../language-reference/keywords/using-directive.md) para los espacios de nombres `System.Collections.Generic` y `System.Linq`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-114">For the examples in this topic, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>

 <span data-ttu-id="a76bc-115">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a76bc-115">**In this topic**</span></span>

- [<span data-ttu-id="a76bc-116">Uso de una colección Simple</span><span class="sxs-lookup"><span data-stu-id="a76bc-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)

- [<span data-ttu-id="a76bc-117">Tipos de colecciones</span><span class="sxs-lookup"><span data-stu-id="a76bc-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)

  - [<span data-ttu-id="a76bc-118">Clases System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="a76bc-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)

  - [<span data-ttu-id="a76bc-119">Clases System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="a76bc-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)

  - [<span data-ttu-id="a76bc-120">Clases System.Collections</span><span class="sxs-lookup"><span data-stu-id="a76bc-120">System.Collections Classes</span></span>](#BKMK_Collections)

- [<span data-ttu-id="a76bc-121">Implementación de una colección de pares de clave/valor</span><span class="sxs-lookup"><span data-stu-id="a76bc-121">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)

- [<span data-ttu-id="a76bc-122">Uso de LINQ para tener acceso a una colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-122">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)

- [<span data-ttu-id="a76bc-123">Ordenar una colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-123">Sorting a Collection</span></span>](#BKMK_Sorting)

- [<span data-ttu-id="a76bc-124">Definición de una colección personalizada</span><span class="sxs-lookup"><span data-stu-id="a76bc-124">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)

- [<span data-ttu-id="a76bc-125">Iteradores</span><span class="sxs-lookup"><span data-stu-id="a76bc-125">Iterators</span></span>](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a><span data-ttu-id="a76bc-126">Uso de una colección Simple</span><span class="sxs-lookup"><span data-stu-id="a76bc-126">Using a Simple Collection</span></span>

<span data-ttu-id="a76bc-127">Los ejemplos de esta sección usan la clase genérica <xref:System.Collections.Generic.List%601>, que le permite trabajar con una lista de objetos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-127">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>

<span data-ttu-id="a76bc-128">En el ejemplo siguiente se crea una lista de cadenas y luego se recorren en iteración mediante una instrucción [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-128">The following example creates a list of strings and then iterates through the strings by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span>

```csharp
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="a76bc-129">Si el contenido de una colección se conoce de antemano, puede usar un *inicializador de colección* para inicializar la colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-129">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="a76bc-130">Para obtener más información, vea [Inicializadores de objeto y colección](../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-130">For more information, see [Object and Collection Initializers](../classes-and-structs/object-and-collection-initializers.md).</span></span>

<span data-ttu-id="a76bc-131">El ejemplo siguiente es el mismo que el ejemplo anterior, excepto que se usa un inicializador de colección para agregar elementos a la colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-131">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="a76bc-132">Puede usar una instrucción [for](../../language-reference/keywords/for.md) en lugar de una instrucción `foreach` para recorrer en iteración una colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-132">You can use a [for](../../language-reference/keywords/for.md) statement instead of a `foreach` statement to iterate through a collection.</span></span> <span data-ttu-id="a76bc-133">Esto se consigue con el acceso a los elementos de la colección mediante la posición de índice.</span><span class="sxs-lookup"><span data-stu-id="a76bc-133">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="a76bc-134">El índice de los elementos comienza en 0 y termina en el número de elementos menos 1.</span><span class="sxs-lookup"><span data-stu-id="a76bc-134">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>

<span data-ttu-id="a76bc-135">El ejemplo siguiente recorre en iteración los elementos de una colección mediante `for` en lugar de `foreach`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-135">The following example iterates through the elements of a collection by using `for` instead of `foreach`.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="a76bc-136">El ejemplo siguiente quita un elemento de la colección especificando el objeto que se quitará.</span><span class="sxs-lookup"><span data-stu-id="a76bc-136">The following example removes an element from the collection by specifying the object to remove.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye
```

<span data-ttu-id="a76bc-137">El ejemplo siguiente quita elementos de una lista genérica.</span><span class="sxs-lookup"><span data-stu-id="a76bc-137">The following example removes elements from a generic list.</span></span> <span data-ttu-id="a76bc-138">En lugar de una instrucción `foreach`, se usa una instrucción [for](../../language-reference/keywords/for.md) que procesa una iteración en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="a76bc-138">Instead of a `foreach` statement, a [for](../../language-reference/keywords/for.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="a76bc-139">Esto es porque el método <xref:System.Collections.Generic.List%601.RemoveAt%2A> hace que los elementos después de un elemento quitado tengan un valor de índice inferior.</span><span class="sxs-lookup"><span data-stu-id="a76bc-139">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>

```csharp
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// Remove odd numbers.
for (var index = numbers.Count - 1; index >= 0; index--)
{
    if (numbers[index] % 2 == 1)
    {
        // Remove the element by specifying
        // the zero-based index in the list.
        numbers.RemoveAt(index);
    }
}

// Iterate through the list.
// A lambda expression is placed in the ForEach method
// of the List(T) object.
numbers.ForEach(
    number => Console.Write(number + " "));
// Output: 0 2 4 6 8
```

<span data-ttu-id="a76bc-140">Para el tipo de elementos de <xref:System.Collections.Generic.List%601>, también puede definir su propia clase.</span><span class="sxs-lookup"><span data-stu-id="a76bc-140">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="a76bc-141">En el ejemplo siguiente, la clase `Galaxy` que usa <xref:System.Collections.Generic.List%601> se define en el código.</span><span class="sxs-lookup"><span data-stu-id="a76bc-141">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>

```csharp
private static void IterateThroughList()
{
    var theGalaxies = new List<Galaxy>
        {
            new Galaxy() { Name="Tadpole", MegaLightYears=400},
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},
            new Galaxy() { Name="Milky Way", MegaLightYears=0},
            new Galaxy() { Name="Andromeda", MegaLightYears=3}
        };

    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);
    }

    // Output:
    //  Tadpole  400
    //  Pinwheel  25
    //  Milky Way  0
    //  Andromeda  3
}

public class Galaxy
{
    public string Name { get; set; }
    public int MegaLightYears { get; set; }
}
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a><span data-ttu-id="a76bc-142">Tipos de colecciones</span><span class="sxs-lookup"><span data-stu-id="a76bc-142">Kinds of Collections</span></span>

<span data-ttu-id="a76bc-143">.NET Framework proporciona muchas colecciones comunes.</span><span class="sxs-lookup"><span data-stu-id="a76bc-143">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="a76bc-144">Cada tipo de colección está diseñado para un fin específico.</span><span class="sxs-lookup"><span data-stu-id="a76bc-144">Each type of collection is designed for a specific purpose.</span></span>

<span data-ttu-id="a76bc-145">En esta sección se describen algunas de las clases de colecciones comunes:</span><span class="sxs-lookup"><span data-stu-id="a76bc-145">Some of the common collection classes are described in this section:</span></span>

- <span data-ttu-id="a76bc-146">Clases <xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="a76bc-146"><xref:System.Collections.Generic> classes</span></span>

- <span data-ttu-id="a76bc-147">Clases <xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="a76bc-147"><xref:System.Collections.Concurrent> classes</span></span>

- <span data-ttu-id="a76bc-148">Clases <xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="a76bc-148"><xref:System.Collections> classes</span></span>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="a76bc-149">Clases System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="a76bc-149">System.Collections.Generic Classes</span></span>

<span data-ttu-id="a76bc-150">Puede crear una colección genérica mediante una de las clases del espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-150">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="a76bc-151">Una colección genérica es útil cuando todos los elementos de la colección tienen el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="a76bc-151">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="a76bc-152">Una colección genérica exige el establecimiento de fuertes tipos al permitir agregar solo los tipos de datos deseados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-152">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>

<span data-ttu-id="a76bc-153">En la tabla siguiente se enumeran algunas de las clases usadas con frecuencia del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a76bc-153">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="a76bc-154">Clase</span><span class="sxs-lookup"><span data-stu-id="a76bc-154">Class</span></span>|<span data-ttu-id="a76bc-155">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a76bc-155">Description</span></span>|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="a76bc-156">Representa una colección de pares de clave y valor que se organizan según la clave.</span><span class="sxs-lookup"><span data-stu-id="a76bc-156">Represents a collection of key/value pairs that are organized based on the key.</span></span>|
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="a76bc-157">Representa una lista de objetos a los que puede tener acceso el índice.</span><span class="sxs-lookup"><span data-stu-id="a76bc-157">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="a76bc-158">Proporciona métodos para buscar, ordenar y modificar listas.</span><span class="sxs-lookup"><span data-stu-id="a76bc-158">Provides methods to search, sort, and modify lists.</span></span>|
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="a76bc-159">Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).</span><span class="sxs-lookup"><span data-stu-id="a76bc-159">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="a76bc-160">Representa una colección de pares clave-valor que se ordenan por claves según la implementación de <xref:System.Collections.Generic.IComparer%601> asociada.</span><span class="sxs-lookup"><span data-stu-id="a76bc-160">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="a76bc-161">Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).</span><span class="sxs-lookup"><span data-stu-id="a76bc-161">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="a76bc-162">Para obtener más información, vea [Tipos de colección utilizados normalmente](../../../standard/collections/commonly-used-collection-types.md), [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md) y <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-162">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic>.</span></span>

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="a76bc-163">Clases System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="a76bc-163">System.Collections.Concurrent Classes</span></span>

<span data-ttu-id="a76bc-164">En .NET Framework 4 o posterior, las colecciones del espacio de nombres <xref:System.Collections.Concurrent> proporcionan operaciones eficaces y seguras para subprocesos con el fin de obtener acceso a los elementos de la colección desde varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a76bc-164">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>

<span data-ttu-id="a76bc-165">Las clases del espacio de nombres <xref:System.Collections.Concurrent> deben usarse en lugar de los tipos correspondientes de los espacios de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> y <xref:System.Collections?displayProperty=nameWithType> cada vez que varios subprocesos tengan acceso de manera simultánea a la colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-165">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="a76bc-166">Para obtener más información, vea [Colecciones seguras para subprocesos](../../../standard/collections/thread-safe/index.md) y <xref:System.Collections.Concurrent>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-166">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>

<span data-ttu-id="a76bc-167">Algunas clases incluidas en el espacio de nombres <xref:System.Collections.Concurrent> son <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-167">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a><span data-ttu-id="a76bc-168">Clases System.Collections</span><span class="sxs-lookup"><span data-stu-id="a76bc-168">System.Collections Classes</span></span>

<span data-ttu-id="a76bc-169">Las clases del espacio de nombres <xref:System.Collections?displayProperty=nameWithType> no almacenan los elementos como objetos de tipo específico, sino como objetos del tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-169">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>

<span data-ttu-id="a76bc-170">Siempre que sea posible, debe usar las colecciones genéricas del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> o del espacio de nombres <xref:System.Collections.Concurrent> en lugar de los tipos heredados del espacio de nombres `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-170">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>

<span data-ttu-id="a76bc-171">En la siguiente tabla se enumeran algunas de las clases usadas con frecuencia en el espacio de nombres `System.Collections`:</span><span class="sxs-lookup"><span data-stu-id="a76bc-171">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>

|<span data-ttu-id="a76bc-172">Clase</span><span class="sxs-lookup"><span data-stu-id="a76bc-172">Class</span></span>|<span data-ttu-id="a76bc-173">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a76bc-173">Description</span></span>|
|---|---|
|<xref:System.Collections.ArrayList>|<span data-ttu-id="a76bc-174">Representa una matriz cuyo tamaño aumenta dinámicamente cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="a76bc-174">Represents an array of objects whose size is dynamically increased as required.</span></span>|
|<xref:System.Collections.Hashtable>|<span data-ttu-id="a76bc-175">Representa una colección de pares de clave y valor que se organizan por código hash de la clave.</span><span class="sxs-lookup"><span data-stu-id="a76bc-175">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|
|<xref:System.Collections.Queue>|<span data-ttu-id="a76bc-176">Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).</span><span class="sxs-lookup"><span data-stu-id="a76bc-176">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Stack>|<span data-ttu-id="a76bc-177">Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).</span><span class="sxs-lookup"><span data-stu-id="a76bc-177">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="a76bc-178">El espacio de nombres <xref:System.Collections.Specialized> proporciona clases de colección especializadas y fuertemente tipadas como, por ejemplo, colecciones de solo cadena y diccionarios híbridos y de lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="a76bc-178">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="a76bc-179">Implementación de una colección de pares de clave/valor</span><span class="sxs-lookup"><span data-stu-id="a76bc-179">Implementing a Collection of Key/Value Pairs</span></span>

<span data-ttu-id="a76bc-180">La colección genérica <xref:System.Collections.Generic.Dictionary%602> le permite tener acceso a los elementos de una colección con la clave de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="a76bc-180">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="a76bc-181">Cada adición al diccionario consta de un valor y de su clave asociada.</span><span class="sxs-lookup"><span data-stu-id="a76bc-181">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="a76bc-182">Recuperar un valor usando su clave es rápido porque la clase `Dictionary` se implementa como una tabla hash.</span><span class="sxs-lookup"><span data-stu-id="a76bc-182">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>

<span data-ttu-id="a76bc-183">En el ejemplo siguiente se crea una colección `Dictionary` y se recorre en iteración el diccionario usando una instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-183">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `foreach` statement.</span></span>

```csharp
private static void IterateThruDictionary()
{
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements)
    {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

private static Dictionary<string, Element> BuildDictionary()
{
    var elements = new Dictionary<string, Element>();

    AddToDictionary(elements, "K", "Potassium", 19);
    AddToDictionary(elements, "Ca", "Calcium", 20);
    AddToDictionary(elements, "Sc", "Scandium", 21);
    AddToDictionary(elements, "Ti", "Titanium", 22);

    return elements;
}

private static void AddToDictionary(Dictionary<string, Element> elements,
    string symbol, string name, int atomicNumber)
{
    Element theElement = new Element();

    theElement.Symbol = symbol;
    theElement.Name = name;
    theElement.AtomicNumber = atomicNumber;

    elements.Add(key: theElement.Symbol, value: theElement);
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<span data-ttu-id="a76bc-184">Para usar un inicializador de colección para compilar la colección `Dictionary`, puede reemplazar los métodos `BuildDictionary` y `AddToDictionary` por el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="a76bc-184">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>

```csharp
private static Dictionary<string, Element> BuildDictionary2()
{
    return new Dictionary<string, Element>
    {
        {"K",
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        {"Ca",
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        {"Sc",
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        {"Ti",
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}
```

<span data-ttu-id="a76bc-185">En el ejemplo siguiente se usa el método <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> y la propiedad <xref:System.Collections.Generic.Dictionary%602.Item%2A> de `Dictionary` para encontrar rápidamente un elemento por clave.</span><span class="sxs-lookup"><span data-stu-id="a76bc-185">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="a76bc-186">La propiedad `Item` le permite tener acceso a un elemento de la colección `elements` usando `elements[symbol]` en C#.</span><span class="sxs-lookup"><span data-stu-id="a76bc-186">The `Item` property enables you to access an item in the `elements` collection by using the `elements[symbol]` in C#.</span></span>

```csharp
private static void FindInDictionary(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    if (elements.ContainsKey(symbol) == false)
    {
        Console.WriteLine(symbol + " not found");
    }
    else
    {
        Element theElement = elements[symbol];
        Console.WriteLine("found: " + theElement.Name);
    }
}
```

<span data-ttu-id="a76bc-187">En el ejemplo siguiente se usa en su lugar el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para encontrar rápidamente un elemento por clave.</span><span class="sxs-lookup"><span data-stu-id="a76bc-187">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>

```csharp
private static void FindInDictionary2(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    Element theElement = null;
    if (elements.TryGetValue(symbol, out theElement) == false)
        Console.WriteLine(symbol + " not found");
    else
        Console.WriteLine("found: " + theElement.Name);
}
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="a76bc-188">Uso de LINQ para tener acceso a una colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-188">Using LINQ to Access a Collection</span></span>

<span data-ttu-id="a76bc-189">LINQ (Language-Integrated Query) puede usar para tener acceso a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="a76bc-189">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="a76bc-190">Las consultas LINQ proporcionan capacidades de filtrado, ordenación y agrupación.</span><span class="sxs-lookup"><span data-stu-id="a76bc-190">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="a76bc-191">Para obtener más información, vea [Introducción a LINQ en C#](/dotnet/csharp/programming-guide/concepts/linq/).</span><span class="sxs-lookup"><span data-stu-id="a76bc-191">For more information, see  [Getting Started with LINQ in C#](/dotnet/csharp/programming-guide/concepts/linq/).</span></span>

<span data-ttu-id="a76bc-192">El ejemplo siguiente ejecuta una consulta LINQ en una `List` genérica.</span><span class="sxs-lookup"><span data-stu-id="a76bc-192">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="a76bc-193">La consulta LINQ devuelve otra colección que contiene los resultados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-193">The LINQ query returns a different collection that contains the results.</span></span>

```csharp
private static void ShowLINQ()
{
    List<Element> elements = BuildList();

    // LINQ Query.
    var subset = from theElement in elements
                 where theElement.AtomicNumber < 22
                 orderby theElement.Name
                 select theElement;

    foreach (Element theElement in subset)
    {
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);
    }

    // Output:
    //  Calcium 20
    //  Potassium 19
    //  Scandium 21
}

private static List<Element> BuildList()
{
    return new List<Element>
    {
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a><span data-ttu-id="a76bc-194">Ordenar una colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-194">Sorting a Collection</span></span>

<span data-ttu-id="a76bc-195">En el ejemplo siguiente se muestra un procedimiento para ordenar una colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-195">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="a76bc-196">El ejemplo ordena las instancias de la clase `Car` que se almacenan en un <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-196">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="a76bc-197">La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-197">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>

<span data-ttu-id="a76bc-198">Cada llamada al método <xref:System.IComparable%601.CompareTo%2A> realiza una comparación única que se usa para la ordenación.</span><span class="sxs-lookup"><span data-stu-id="a76bc-198">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="a76bc-199">El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto.</span><span class="sxs-lookup"><span data-stu-id="a76bc-199">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="a76bc-200">El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales.</span><span class="sxs-lookup"><span data-stu-id="a76bc-200">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="a76bc-201">Esto permite definir en el código los criterios de mayor que, menor que e igual.</span><span class="sxs-lookup"><span data-stu-id="a76bc-201">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>

<span data-ttu-id="a76bc-202">En el método `ListCars`, la instrucción `cars.Sort()` ordena la lista.</span><span class="sxs-lookup"><span data-stu-id="a76bc-202">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="a76bc-203">Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que se llame automáticamente al método `CompareTo` para los objetos `Car` de `List`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-203">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>

```csharp
private static void ListCars()
{
    var cars = new List<Car>
    {
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},
        { new Car() { Name = "car2", Color = "red", Speed = 50}},
        { new Car() { Name = "car3", Color = "green", Speed = 10}},
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},
        { new Car() { Name = "car6", Color = "red", Speed = 60}},
        { new Car() { Name = "car7", Color = "green", Speed = 50}}
    };

    // Sort the cars by color alphabetically, and then by speed
    // in descending order.
    cars.Sort();

    // View all of the cars.
    foreach (Car thisCar in cars)
    {
        Console.Write(thisCar.Color.PadRight(5) + " ");
        Console.Write(thisCar.Speed.ToString() + " ");
        Console.Write(thisCar.Name);
        Console.WriteLine();
    }

    // Output:
    //  blue  50 car4
    //  blue  30 car5
    //  blue  20 car1
    //  green 50 car7
    //  green 10 car3
    //  red   60 car6
    //  red   50 car2
}

public class Car : IComparable<Car>
{
    public string Name { get; set; }
    public int Speed { get; set; }
    public string Color { get; set; }

    public int CompareTo(Car other)
    {
        // A call to this method makes a single comparison that is
        // used for sorting.

        // Determine the relative order of the objects being compared.
        // Sort by color alphabetically, and then by speed in
        // descending order.

        // Compare the colors.
        int compare;
        compare = String.Compare(this.Color, other.Color, true);

        // If the colors are the same, compare the speeds.
        if (compare == 0)
        {
            compare = this.Speed.CompareTo(other.Speed);

            // Use descending order for speed.
            compare = -compare;
        }

        return compare;
    }
}
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a><span data-ttu-id="a76bc-204">Definición de una colección personalizada</span><span class="sxs-lookup"><span data-stu-id="a76bc-204">Defining a Custom Collection</span></span>

<span data-ttu-id="a76bc-205">Puede definir una colección implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-205">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span>

<span data-ttu-id="a76bc-206">Aunque puede definir una colección personalizada, es mejor usar las colecciones incluidas en .NET Framework. Estas colecciones se describen en la sección [Tipos de colecciones](#BKMK_KindsOfCollections) de este tema.</span><span class="sxs-lookup"><span data-stu-id="a76bc-206">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](#BKMK_KindsOfCollections) earlier in this topic.</span></span>

<span data-ttu-id="a76bc-207">En el siguiente ejemplo se define una clase de colección personalizada denominada `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-207">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="a76bc-208">Esta clase implementa la interfaz <xref:System.Collections.IEnumerable> que requiere implementar el método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="a76bc-208">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>

<span data-ttu-id="a76bc-209">El método `GetEnumerator` devuelve una instancia de la clase `ColorEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-209">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="a76bc-210">`ColorEnumerator` implementa la interfaz <xref:System.Collections.IEnumerator>, que requiere que la propiedad <xref:System.Collections.IEnumerator.Current%2A>, el método <xref:System.Collections.IEnumerator.MoveNext%2A> y el método <xref:System.Collections.IEnumerator.Reset%2A> estén implementados.</span><span class="sxs-lookup"><span data-stu-id="a76bc-210">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>

```csharp
private static void ListColors()
{
    var colors = new AllColors();

    foreach (Color theColor in colors)
    {
        Console.Write(theColor.Name + " ");
    }
    Console.WriteLine();
    // Output: red blue green
}

// Collection class.
public class AllColors : System.Collections.IEnumerable
{
    Color[] _colors =
    {
        new Color() { Name = "red" },
        new Color() { Name = "blue" },
        new Color() { Name = "green" }
    };

    public System.Collections.IEnumerator GetEnumerator()
    {
        return new ColorEnumerator(_colors);

        // Instead of creating a custom enumerator, you could
        // use the GetEnumerator of the array.
        //return _colors.GetEnumerator();
    }

    // Custom enumerator.
    private class ColorEnumerator : System.Collections.IEnumerator
    {
        private Color[] _colors;
        private int _position = -1;

        public ColorEnumerator(Color[] colors)
        {
            _colors = colors;
        }

        object System.Collections.IEnumerator.Current
        {
            get
            {
                return _colors[_position];
            }
        }

        bool System.Collections.IEnumerator.MoveNext()
        {
            _position++;
            return (_position < _colors.Length);
        }

        void System.Collections.IEnumerator.Reset()
        {
            _position = -1;
        }
    }
}

// Element class.
public class Color
{
    public string Name { get; set; }
}
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a><span data-ttu-id="a76bc-211">Iterators</span><span class="sxs-lookup"><span data-stu-id="a76bc-211">Iterators</span></span>

<span data-ttu-id="a76bc-212">Los *iteradores* se usan para efectuar una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="a76bc-212">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="a76bc-213">Un iterador puede ser un método o un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-213">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="a76bc-214">Un iterador usa una instrucción [yield return](../../language-reference/keywords/yield.md) para devolver cada elemento de la colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="a76bc-214">An iterator uses a [yield return](../../language-reference/keywords/yield.md) statement to return each element of the collection one at a time.</span></span>

<span data-ttu-id="a76bc-215">Llame a un iterador mediante una instrucción [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-215">You call an iterator by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="a76bc-216">Cada iteración del bucle `foreach` llama al iterador.</span><span class="sxs-lookup"><span data-stu-id="a76bc-216">Each iteration of the `foreach` loop calls the iterator.</span></span> <span data-ttu-id="a76bc-217">Cuando se alcanza una instrucción `yield return` en el iterador, se devuelve una expresión y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="a76bc-217">When a `yield return` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="a76bc-218">La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.</span><span class="sxs-lookup"><span data-stu-id="a76bc-218">Execution is restarted from that location the next time that the iterator is called.</span></span>

<span data-ttu-id="a76bc-219">Para obtener más información, vea [Iteradores (C#)](./iterators.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-219">For more information, see [Iterators (C#)](./iterators.md).</span></span>

<span data-ttu-id="a76bc-220">El siguiente ejemplo usa el método del iterador.</span><span class="sxs-lookup"><span data-stu-id="a76bc-220">The following example uses an iterator method.</span></span> <span data-ttu-id="a76bc-221">El método del iterador tiene una instrucción `yield return` que se encuentra dentro de un bucle [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="a76bc-221">The iterator method has a `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="a76bc-222">En el método `ListEvenNumbers`, cada iteración del cuerpo de la instrucción `foreach` crea una llamada al método iterador, que continúa con la siguiente instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="a76bc-222">In the `ListEvenNumbers` method, each iteration of the `foreach` statement body creates a call to the iterator method, which proceeds to the next `yield return` statement.</span></span>

```csharp
private static void ListEvenNumbers()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    Console.WriteLine();
    // Output: 6 8 10 12 14 16 18
}

private static IEnumerable<int> EvenSequence(
    int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (var number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a76bc-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="a76bc-223">See also</span></span>

- [<span data-ttu-id="a76bc-224">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-224">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="a76bc-225">Conceptos de programación (C#)</span><span class="sxs-lookup"><span data-stu-id="a76bc-225">Programming Concepts (C#)</span></span>](./index.md)
- [<span data-ttu-id="a76bc-226">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a76bc-226">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="a76bc-227">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="a76bc-227">LINQ to Objects (C#)</span></span>](./linq/linq-to-objects.md)
- [<span data-ttu-id="a76bc-228">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="a76bc-228">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/parallel-linq-plinq.md)
- [<span data-ttu-id="a76bc-229">Colecciones y estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="a76bc-229">Collections and Data Structures</span></span>](../../../standard/collections/index.md)
- [<span data-ttu-id="a76bc-230">Seleccionar una clase de colección</span><span class="sxs-lookup"><span data-stu-id="a76bc-230">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)
- [<span data-ttu-id="a76bc-231">Comparaciones y ordenaciones en colecciones</span><span class="sxs-lookup"><span data-stu-id="a76bc-231">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [<span data-ttu-id="a76bc-232">Cuándo utilizar colecciones genéricas</span><span class="sxs-lookup"><span data-stu-id="a76bc-232">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
