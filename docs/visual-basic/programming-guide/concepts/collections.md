---
title: Recopilaciones
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: 91c6048caf622f21a02032bac31cb2ba5565c54c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551072"
---
# <a name="collections-visual-basic"></a><span data-ttu-id="a8794-102">Colecciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8794-102">Collections (Visual Basic)</span></span>

<span data-ttu-id="a8794-103">Para muchas aplicaciones, puede que desee crear y administrar grupos de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a8794-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="a8794-104">Existen dos formas de agrupar objetos: mediante la creación de matrices de objetos y con la creación de colecciones de objetos.</span><span class="sxs-lookup"><span data-stu-id="a8794-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>

<span data-ttu-id="a8794-105">Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="a8794-105">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="a8794-106">Para obtener información sobre las matrices, vea [Matrices](../language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8794-106">For information about arrays, see [Arrays](../language-features/arrays/index.md).</span></span>

<span data-ttu-id="a8794-107">Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos.</span><span class="sxs-lookup"><span data-stu-id="a8794-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="a8794-108">A diferencia de las matrices, el grupo de objetos con el que trabaja puede aumentar y reducirse de manera dinámica a medida que cambian las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8794-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="a8794-109">Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>

<span data-ttu-id="a8794-110">Una colección es una clase, por lo que debe declarar una instancia de la clase para poder agregar elementos a dicha colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>

<span data-ttu-id="a8794-111">Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8794-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a8794-112">Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="a8794-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="a8794-113">Cuando recupera un elemento de una colección genérica, no tiene que determinar su tipo de datos ni convertirlo.</span><span class="sxs-lookup"><span data-stu-id="a8794-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>

> [!NOTE]
> <span data-ttu-id="a8794-114">Para ver los ejemplos de este tema, incluya instrucciones [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para los `System.Collections.Generic` espacios de `System.Linq` nombres y.</span><span class="sxs-lookup"><span data-stu-id="a8794-114">For the examples in this topic, include [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a><span data-ttu-id="a8794-115">Uso de una colección Simple</span><span class="sxs-lookup"><span data-stu-id="a8794-115">Using a Simple Collection</span></span>

<span data-ttu-id="a8794-116">Los ejemplos de esta sección usan la clase genérica <xref:System.Collections.Generic.List%601>, que le permite trabajar con una lista de objetos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="a8794-116">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>

<span data-ttu-id="a8794-117">En el ejemplo siguiente se crea una lista de cadenas y, a continuación, se recorre en iteración las cadenas mediante una... [ Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="a8794-117">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../language-reference/statements/for-each-next-statement.md) statement.</span></span>

```vb
' Create a list of strings.
Dim salmons As New List(Of String)
salmons.Add("chinook")
salmons.Add("coho")
salmons.Add("pink")
salmons.Add("sockeye")

' Iterate through the list.
For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

<span data-ttu-id="a8794-118">Si el contenido de una colección se conoce de antemano, puede usar un *inicializador de colección* para inicializar la colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-118">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="a8794-119">Para obtener más información, vea [Inicializadores de colección](../language-features/collection-initializers/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8794-119">For more information, see [Collection Initializers](../language-features/collection-initializers/index.md).</span></span>

<span data-ttu-id="a8794-120">El ejemplo siguiente es el mismo que el ejemplo anterior, excepto que se usa un inicializador de colección para agregar elementos a la colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-120">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

<span data-ttu-id="a8794-121">Puede usar una [... Instrucción Next](../../language-reference/statements/for-next-statement.md) en lugar de una `For Each` instrucción para recorrer en iteración una colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-121">You can use a [For…Next](../../language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="a8794-122">Esto se consigue con el acceso a los elementos de la colección mediante la posición de índice.</span><span class="sxs-lookup"><span data-stu-id="a8794-122">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="a8794-123">El índice de los elementos comienza en 0 y termina en el número de elementos menos 1.</span><span class="sxs-lookup"><span data-stu-id="a8794-123">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>

<span data-ttu-id="a8794-124">El ejemplo siguiente recorre en iteración los elementos de una colección mediante `For…Next` en lugar de `For Each`.</span><span class="sxs-lookup"><span data-stu-id="a8794-124">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

<span data-ttu-id="a8794-125">El ejemplo siguiente quita un elemento de la colección especificando el objeto que se quitará.</span><span class="sxs-lookup"><span data-stu-id="a8794-125">The following example removes an element from the collection by specifying the object to remove.</span></span>

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

' Remove an element in the list by specifying
' the object.
salmons.Remove("coho")

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook pink sockeye
```

<span data-ttu-id="a8794-126">El ejemplo siguiente quita elementos de una lista genérica.</span><span class="sxs-lookup"><span data-stu-id="a8794-126">The following example removes elements from a generic list.</span></span> <span data-ttu-id="a8794-127">En lugar de una `For Each` instrucción, una instrucción [for... ](../../language-reference/statements/for-next-statement.md) Se usa la siguiente instrucción que recorre en iteración en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="a8794-127">Instead of a `For Each` statement, a [For…Next](../../language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="a8794-128">Esto es porque el método <xref:System.Collections.Generic.List%601.RemoveAt%2A> hace que los elementos después de un elemento quitado tengan un valor de índice inferior.</span><span class="sxs-lookup"><span data-stu-id="a8794-128">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>

```vb
Dim numbers As New List(Of Integer) From
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

' Remove odd numbers.
For index As Integer = numbers.Count - 1 To 0 Step -1
    If numbers(index) Mod 2 = 1 Then
        ' Remove the element by specifying
        ' the zero-based index in the list.
        numbers.RemoveAt(index)
    End If
Next

' Iterate through the list.
' A lambda expression is placed in the ForEach method
' of the List(T) object.
numbers.ForEach(
    Sub(number) Console.Write(number & " "))
' Output: 0 2 4 6 8
```

<span data-ttu-id="a8794-129">Para el tipo de elementos de <xref:System.Collections.Generic.List%601>, también puede definir su propia clase.</span><span class="sxs-lookup"><span data-stu-id="a8794-129">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="a8794-130">En el ejemplo siguiente, la clase `Galaxy` que usa <xref:System.Collections.Generic.List%601> se define en el código.</span><span class="sxs-lookup"><span data-stu-id="a8794-130">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>

```vb
Private Sub IterateThroughList()
    Dim theGalaxies As New List(Of Galaxy) From
        {
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}
        }

    For Each theGalaxy In theGalaxies
        With theGalaxy
            Console.WriteLine(.Name & "  " & .MegaLightYears)
        End With
    Next

    ' Output:
    '  Tadpole  400
    '  Pinwheel  25
    '  Milky Way  0
    '  Andromeda  3
End Sub

Public Class Galaxy
    Public Property Name As String
    Public Property MegaLightYears As Integer
End Class
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a><span data-ttu-id="a8794-131">Tipos de colecciones</span><span class="sxs-lookup"><span data-stu-id="a8794-131">Kinds of Collections</span></span>

<span data-ttu-id="a8794-132">.NET Framework proporciona muchas colecciones comunes.</span><span class="sxs-lookup"><span data-stu-id="a8794-132">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="a8794-133">Cada tipo de colección está diseñado para un fin específico.</span><span class="sxs-lookup"><span data-stu-id="a8794-133">Each type of collection is designed for a specific purpose.</span></span>

<span data-ttu-id="a8794-134">En esta sección se describen algunas de las clases de colecciones comunes:</span><span class="sxs-lookup"><span data-stu-id="a8794-134">Some of the common collection classes are described in this section:</span></span>

- <span data-ttu-id="a8794-135">Clases <xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="a8794-135"><xref:System.Collections.Generic> classes</span></span>

- <span data-ttu-id="a8794-136">Clases <xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="a8794-136"><xref:System.Collections.Concurrent> classes</span></span>

- <span data-ttu-id="a8794-137">Clases <xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="a8794-137"><xref:System.Collections> classes</span></span>

- <span data-ttu-id="a8794-138">Clase `Collection` de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8794-138">Visual Basic `Collection` class</span></span>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="a8794-139">Clases System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="a8794-139">System.Collections.Generic Classes</span></span>

<span data-ttu-id="a8794-140">Puede crear una colección genérica mediante una de las clases del espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="a8794-140">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="a8794-141">Una colección genérica es útil cuando todos los elementos de la colección tienen el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="a8794-141">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="a8794-142">Una colección genérica exige el establecimiento de fuertes tipos al permitir agregar solo los tipos de datos deseados.</span><span class="sxs-lookup"><span data-stu-id="a8794-142">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>

<span data-ttu-id="a8794-143">En la tabla siguiente se enumeran algunas de las clases usadas con frecuencia del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a8794-143">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="a8794-144">Clase</span><span class="sxs-lookup"><span data-stu-id="a8794-144">Class</span></span>|<span data-ttu-id="a8794-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8794-145">Description</span></span>|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="a8794-146">Representa una colección de pares de clave y valor que se organizan según la clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-146">Represents a collection of key/value pairs that are organized based on the key.</span></span>|
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="a8794-147">Representa una lista de objetos a los que puede tener acceso el índice.</span><span class="sxs-lookup"><span data-stu-id="a8794-147">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="a8794-148">Proporciona métodos para buscar, ordenar y modificar listas.</span><span class="sxs-lookup"><span data-stu-id="a8794-148">Provides methods to search, sort, and modify lists.</span></span>|
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="a8794-149">Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).</span><span class="sxs-lookup"><span data-stu-id="a8794-149">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="a8794-150">Representa una colección de pares clave-valor que se ordenan por claves según la implementación de <xref:System.Collections.Generic.IComparer%601> asociada.</span><span class="sxs-lookup"><span data-stu-id="a8794-150">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="a8794-151">Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).</span><span class="sxs-lookup"><span data-stu-id="a8794-151">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="a8794-152">Para obtener más información, vea [Tipos de colección utilizados normalmente](../../../standard/collections/commonly-used-collection-types.md), [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md) y <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8794-152">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="a8794-153">Clases System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="a8794-153">System.Collections.Concurrent Classes</span></span>

<span data-ttu-id="a8794-154">En .NET Framework 4 o posterior, las colecciones del espacio de nombres <xref:System.Collections.Concurrent> proporcionan operaciones eficaces y seguras para subprocesos con el fin de obtener acceso a los elementos de la colección desde varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a8794-154">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>

<span data-ttu-id="a8794-155">Las clases del espacio de nombres <xref:System.Collections.Concurrent> deben usarse en lugar de los tipos correspondientes de los espacios de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> y <xref:System.Collections?displayProperty=nameWithType> cada vez que varios subprocesos tengan acceso de manera simultánea a la colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-155">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="a8794-156">Para obtener más información, vea [Colecciones seguras para subprocesos](../../../standard/collections/thread-safe/index.md) y <xref:System.Collections.Concurrent>.</span><span class="sxs-lookup"><span data-stu-id="a8794-156">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>

<span data-ttu-id="a8794-157">Algunas clases incluidas en el espacio de nombres <xref:System.Collections.Concurrent> son <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="a8794-157">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a><span data-ttu-id="a8794-158">Clases System.Collections</span><span class="sxs-lookup"><span data-stu-id="a8794-158">System.Collections Classes</span></span>

<span data-ttu-id="a8794-159">Las clases del espacio de nombres <xref:System.Collections?displayProperty=nameWithType> no almacenan los elementos como objetos de tipo específico, sino como objetos del tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="a8794-159">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>

<span data-ttu-id="a8794-160">Siempre que sea posible, debe usar las colecciones genéricas del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> o del espacio de nombres <xref:System.Collections.Concurrent> en lugar de los tipos heredados del espacio de nombres `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="a8794-160">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>

<span data-ttu-id="a8794-161">En la siguiente tabla se enumeran algunas de las clases usadas con frecuencia en el espacio de nombres `System.Collections`:</span><span class="sxs-lookup"><span data-stu-id="a8794-161">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>

|<span data-ttu-id="a8794-162">Clase</span><span class="sxs-lookup"><span data-stu-id="a8794-162">Class</span></span>|<span data-ttu-id="a8794-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8794-163">Description</span></span>|
|---|---|
|<xref:System.Collections.ArrayList>|<span data-ttu-id="a8794-164">Representa una matriz cuyo tamaño aumenta dinámicamente cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="a8794-164">Represents an array of objects whose size is dynamically increased as required.</span></span>|
|<xref:System.Collections.Hashtable>|<span data-ttu-id="a8794-165">Representa una colección de pares de clave y valor que se organizan por código hash de la clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-165">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|
|<xref:System.Collections.Queue>|<span data-ttu-id="a8794-166">Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).</span><span class="sxs-lookup"><span data-stu-id="a8794-166">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Stack>|<span data-ttu-id="a8794-167">Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).</span><span class="sxs-lookup"><span data-stu-id="a8794-167">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="a8794-168">El espacio de nombres <xref:System.Collections.Specialized> proporciona clases de colección especializadas y fuertemente tipadas como, por ejemplo, colecciones de solo cadena y diccionarios híbridos y de lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="a8794-168">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a><span data-ttu-id="a8794-169">Clase de colección de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8794-169">Visual Basic Collection Class</span></span>

<span data-ttu-id="a8794-170">Puede usar la clase de Visual Basic <xref:Microsoft.VisualBasic.Collection> para tener acceso a un elemento de colección mediante un índice numérico o una clave `String`.</span><span class="sxs-lookup"><span data-stu-id="a8794-170">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="a8794-171">Puede agregar elementos a un objeto de colección especificando o sin especificar clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-171">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="a8794-172">Si agrega un elemento sin clave, debe usar su índice numérico para tener acceso a dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="a8794-172">If you add an item without a key, you must use its numeric index to access it.</span></span>

<span data-ttu-id="a8794-173">La clase de Visual Basic `Collection` almacena todos sus elementos como de tipo `Object`, por lo que puede agregar un elemento de cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a8794-173">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="a8794-174">No hay ningún método de protección contra los tipos de datos inadecuados agregados.</span><span class="sxs-lookup"><span data-stu-id="a8794-174">There is no safeguard against inappropriate data types being added.</span></span>

<span data-ttu-id="a8794-175">Cuando se usa la clase de Visual Basic `Collection`, el primer elemento de una colección tiene un índice de 1.</span><span class="sxs-lookup"><span data-stu-id="a8794-175">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="a8794-176">Esto difiere de las clases de colección de .NET Framework, para las cuales el índice inicial es 0.</span><span class="sxs-lookup"><span data-stu-id="a8794-176">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>

<span data-ttu-id="a8794-177">Siempre que sea posible, debe usar las colecciones genéricas del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> o del espacio de nombres <xref:System.Collections.Concurrent> en lugar de la clase de Visual Basic `Collection`.</span><span class="sxs-lookup"><span data-stu-id="a8794-177">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>

<span data-ttu-id="a8794-178">Para obtener más información, vea <xref:Microsoft.VisualBasic.Collection>.</span><span class="sxs-lookup"><span data-stu-id="a8794-178">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="a8794-179">Implementación de una colección de pares de clave/valor</span><span class="sxs-lookup"><span data-stu-id="a8794-179">Implementing a Collection of Key/Value Pairs</span></span>

<span data-ttu-id="a8794-180">La colección genérica <xref:System.Collections.Generic.Dictionary%602> le permite tener acceso a los elementos de una colección con la clave de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="a8794-180">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="a8794-181">Cada adición al diccionario consta de un valor y de su clave asociada.</span><span class="sxs-lookup"><span data-stu-id="a8794-181">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="a8794-182">Recuperar un valor usando su clave es rápido porque la clase `Dictionary` se implementa como una tabla hash.</span><span class="sxs-lookup"><span data-stu-id="a8794-182">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>

<span data-ttu-id="a8794-183">En el ejemplo siguiente se crea una colección `Dictionary` y se recorre en iteración el diccionario usando una instrucción `For Each`.</span><span class="sxs-lookup"><span data-stu-id="a8794-183">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>

```vb
Private Sub IterateThroughDictionary()
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    For Each kvp As KeyValuePair(Of String, Element) In elements
        Dim theElement As Element = kvp.Value

        Console.WriteLine("key: " & kvp.Key)
        With theElement
            Console.WriteLine("values: " & .Symbol & " " &
                .Name & " " & .AtomicNumber)
        End With
    Next
End Sub

Private Function BuildDictionary() As Dictionary(Of String, Element)
    Dim elements As New Dictionary(Of String, Element)

    AddToDictionary(elements, "K", "Potassium", 19)
    AddToDictionary(elements, "Ca", "Calcium", 20)
    AddToDictionary(elements, "Sc", "Scandium", 21)
    AddToDictionary(elements, "Ti", "Titanium", 22)

    Return elements
End Function

Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)
    Dim theElement As New Element

    theElement.Symbol = symbol
    theElement.Name = name
    theElement.AtomicNumber = atomicNumber

    elements.Add(Key:=theElement.Symbol, value:=theElement)
End Sub

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

<span data-ttu-id="a8794-184">Para usar un inicializador de colección para compilar la colección `Dictionary`, puede reemplazar los métodos `BuildDictionary` y `AddToDictionary` por el método siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8794-184">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>

```vb
Private Function BuildDictionary2() As Dictionary(Of String, Element)
    Return New Dictionary(Of String, Element) From
        {
            {"K", New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {"Ca", New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {"Sc", New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {"Ti", New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function
```

<span data-ttu-id="a8794-185">En el ejemplo siguiente se usa el método <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> y la propiedad <xref:System.Collections.Generic.Dictionary%602.Item%2A> de `Dictionary` para encontrar rápidamente un elemento por clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-185">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="a8794-186">La `Item` propiedad le permite tener acceso a un elemento de la `elements` colección utilizando el `elements(symbol)` código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8794-186">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>

```vb
Private Sub FindInDictionary(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    If elements.ContainsKey(symbol) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Dim theElement = elements(symbol)
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

<span data-ttu-id="a8794-187">En el ejemplo siguiente se usa en su lugar el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para encontrar rápidamente un elemento por clave.</span><span class="sxs-lookup"><span data-stu-id="a8794-187">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>

```vb
Private Sub FindInDictionary2(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    Dim theElement As Element = Nothing
    If elements.TryGetValue(symbol, theElement) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="a8794-188">Uso de LINQ para tener acceso a una colección</span><span class="sxs-lookup"><span data-stu-id="a8794-188">Using LINQ to Access a Collection</span></span>

<span data-ttu-id="a8794-189">LINQ (Language-Integrated Query) puede usar para tener acceso a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="a8794-189">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="a8794-190">Las consultas LINQ proporcionan capacidades de filtrado, ordenación y agrupación.</span><span class="sxs-lookup"><span data-stu-id="a8794-190">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="a8794-191">Para obtener más información, vea [Introducción con LINQ en Visual Basic](linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="a8794-191">For more information, see [Getting Started with LINQ in Visual Basic](linq/getting-started-with-linq.md).</span></span>

<span data-ttu-id="a8794-192">El ejemplo siguiente ejecuta una consulta LINQ en una `List` genérica.</span><span class="sxs-lookup"><span data-stu-id="a8794-192">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="a8794-193">La consulta LINQ devuelve otra colección que contiene los resultados.</span><span class="sxs-lookup"><span data-stu-id="a8794-193">The LINQ query returns a different collection that contains the results.</span></span>

```vb
Private Sub ShowLINQ()
    Dim elements As List(Of Element) = BuildList()

    ' LINQ Query.
    Dim subset = From theElement In elements
                  Where theElement.AtomicNumber < 22
                  Order By theElement.Name

    For Each theElement In subset
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)
    Next

    ' Output:
    '  Calcium 20
    '  Potassium 19
    '  Scandium 21
End Sub

Private Function BuildList() As List(Of Element)
    Return New List(Of Element) From
        {
            {New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a><span data-ttu-id="a8794-194">Ordenar una colección</span><span class="sxs-lookup"><span data-stu-id="a8794-194">Sorting a Collection</span></span>

<span data-ttu-id="a8794-195">En el ejemplo siguiente se muestra un procedimiento para ordenar una colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-195">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="a8794-196">El ejemplo ordena las instancias de la clase `Car` que se almacenan en un <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a8794-196">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="a8794-197">La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8794-197">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>

<span data-ttu-id="a8794-198">Cada llamada al método <xref:System.IComparable%601.CompareTo%2A> realiza una comparación única que se usa para la ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8794-198">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="a8794-199">El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto.</span><span class="sxs-lookup"><span data-stu-id="a8794-199">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="a8794-200">El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales.</span><span class="sxs-lookup"><span data-stu-id="a8794-200">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="a8794-201">Esto permite definir en el código los criterios de mayor que, menor que e igual.</span><span class="sxs-lookup"><span data-stu-id="a8794-201">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>

<span data-ttu-id="a8794-202">En el método `ListCars`, la instrucción `cars.Sort()` ordena la lista.</span><span class="sxs-lookup"><span data-stu-id="a8794-202">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="a8794-203">Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que se llame automáticamente al método `CompareTo` para los objetos `Car` de `List`.</span><span class="sxs-lookup"><span data-stu-id="a8794-203">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>

```vb
Public Sub ListCars()

    ' Create some new cars.
    Dim cars As New List(Of Car) From
    {
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}
    }

    ' Sort the cars by color alphabetically, and then by speed
    ' in descending order.
    cars.Sort()

    ' View all of the cars.
    For Each thisCar As Car In cars
        Console.Write(thisCar.Color.PadRight(5) & " ")
        Console.Write(thisCar.Speed.ToString & " ")
        Console.Write(thisCar.Name)
        Console.WriteLine()
    Next

    ' Output:
    '  blue  50 car4
    '  blue  30 car5
    '  blue  20 car1
    '  green 50 car7
    '  green 10 car3
    '  red   60 car6
    '  red   50 car2
End Sub

Public Class Car
    Implements IComparable(Of Car)

    Public Property Name As String
    Public Property Speed As Integer
    Public Property Color As String

    Public Function CompareTo(ByVal other As Car) As Integer _
        Implements System.IComparable(Of Car).CompareTo
        ' A call to this method makes a single comparison that is
        ' used for sorting.

        ' Determine the relative order of the objects being compared.
        ' Sort by color alphabetically, and then by speed in
        ' descending order.

        ' Compare the colors.
        Dim compare As Integer
        compare = String.Compare(Me.Color, other.Color, True)

        ' If the colors are the same, compare the speeds.
        If compare = 0 Then
            compare = Me.Speed.CompareTo(other.Speed)

            ' Use descending order for speed.
            compare = -compare
        End If

        Return compare
    End Function
End Class
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a><span data-ttu-id="a8794-204">Definición de una colección personalizada</span><span class="sxs-lookup"><span data-stu-id="a8794-204">Defining a Custom Collection</span></span>

<span data-ttu-id="a8794-205">Puede definir una colección implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="a8794-205">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="a8794-206">Para obtener más información, vea [enumerar una colección](/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a8794-206">For additional information, see [Enumerating a Collection](/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).</span></span>

<span data-ttu-id="a8794-207">Aunque puede definir una colección personalizada, es mejor usar las colecciones incluidas en .NET Framework. Estas colecciones se describen en la sección [Tipos de colecciones](#kinds-of-collections) de este tema.</span><span class="sxs-lookup"><span data-stu-id="a8794-207">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](#kinds-of-collections) earlier in this topic.</span></span>

<span data-ttu-id="a8794-208">En el siguiente ejemplo se define una clase de colección personalizada denominada `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="a8794-208">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="a8794-209">Esta clase implementa la interfaz <xref:System.Collections.IEnumerable> que requiere implementar el método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8794-209">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>

<span data-ttu-id="a8794-210">El método `GetEnumerator` devuelve una instancia de la clase `ColorEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="a8794-210">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="a8794-211">`ColorEnumerator` implementa la interfaz <xref:System.Collections.IEnumerator>, que requiere que la propiedad <xref:System.Collections.IEnumerator.Current%2A>, el método <xref:System.Collections.IEnumerator.MoveNext%2A> y el método <xref:System.Collections.IEnumerator.Reset%2A> estén implementados.</span><span class="sxs-lookup"><span data-stu-id="a8794-211">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>

```vb
Public Sub ListColors()
    Dim colors As New AllColors()

    For Each theColor As Color In colors
        Console.Write(theColor.Name & " ")
    Next
    Console.WriteLine()
    ' Output: red blue green
End Sub

' Collection class.
Public Class AllColors
    Implements System.Collections.IEnumerable

    Private _colors() As Color =
    {
        New Color With {.Name = "red"},
        New Color With {.Name = "blue"},
        New Color With {.Name = "green"}
    }

    Public Function GetEnumerator() As System.Collections.IEnumerator _
        Implements System.Collections.IEnumerable.GetEnumerator

        Return New ColorEnumerator(_colors)

        ' Instead of creating a custom enumerator, you could
        ' use the GetEnumerator of the array.
        'Return _colors.GetEnumerator
    End Function

    ' Custom enumerator.
    Private Class ColorEnumerator
        Implements System.Collections.IEnumerator

        Private _colors() As Color
        Private _position As Integer = -1

        Public Sub New(ByVal colors() As Color)
            _colors = colors
        End Sub

        Public ReadOnly Property Current() As Object _
            Implements System.Collections.IEnumerator.Current
            Get
                Return _colors(_position)
            End Get
        End Property

        Public Function MoveNext() As Boolean _
            Implements System.Collections.IEnumerator.MoveNext
            _position += 1
            Return (_position < _colors.Length)
        End Function

        Public Sub Reset() Implements System.Collections.IEnumerator.Reset
            _position = -1
        End Sub
    End Class
End Class

' Element class.
Public Class Color
    Public Property Name As String
End Class
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a><span data-ttu-id="a8794-212">Iterators</span><span class="sxs-lookup"><span data-stu-id="a8794-212">Iterators</span></span>

<span data-ttu-id="a8794-213">Los *iteradores* se usan para efectuar una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="a8794-213">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="a8794-214">Un iterador puede ser un método o un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="a8794-214">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="a8794-215">Un iterador usa una instrucción [yield](../../language-reference/statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="a8794-215">An iterator uses a [Yield](../../language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>

<span data-ttu-id="a8794-216">Se llama a un iterador mediante un método [for each... Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="a8794-216">You call an iterator by using a [For Each…Next](../../language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="a8794-217">Cada iteración del bucle `For Each` llama al iterador.</span><span class="sxs-lookup"><span data-stu-id="a8794-217">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="a8794-218">Cuando se alcanza una instrucción `Yield` en el iterador, se devuelve una expresión y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="a8794-218">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="a8794-219">La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.</span><span class="sxs-lookup"><span data-stu-id="a8794-219">Execution is restarted from that location the next time that the iterator is called.</span></span>

<span data-ttu-id="a8794-220">Para obtener más información, vea [iteradores (Visual Basic)](iterators.md).</span><span class="sxs-lookup"><span data-stu-id="a8794-220">For more information, see [Iterators (Visual Basic)](iterators.md).</span></span>

<span data-ttu-id="a8794-221">El siguiente ejemplo usa el método del iterador.</span><span class="sxs-lookup"><span data-stu-id="a8794-221">The following example uses an iterator method.</span></span> <span data-ttu-id="a8794-222">El método iterador tiene una `Yield` instrucción que está dentro [de un... Siguiente](../../language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="a8794-222">The iterator method has a `Yield` statement that is inside a [For…Next](../../language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="a8794-223">En el método `ListEvenNumbers`, cada iteración del cuerpo de la instrucción `For Each` crea una llamada al método iterador, que continúa con la siguiente instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="a8794-223">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>

```vb
Public Sub ListEvenNumbers()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    Console.WriteLine()
    ' Output: 6 8 10 12 14 16 18
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As IEnumerable(Of Integer)

' Yield even numbers in the range.
    For number = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="see-also"></a><span data-ttu-id="a8794-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8794-224">See also</span></span>

- [<span data-ttu-id="a8794-225">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="a8794-225">Collection Initializers</span></span>](../language-features/collection-initializers/index.md)
- [<span data-ttu-id="a8794-226">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8794-226">Programming Concepts (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="a8794-227">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a8794-227">Option Strict Statement</span></span>](../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="a8794-228">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8794-228">LINQ to Objects (Visual Basic)</span></span>](linq/linq-to-objects.md)
- [<span data-ttu-id="a8794-229">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="a8794-229">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/introduction-to-plinq.md)
- [<span data-ttu-id="a8794-230">Colecciones y estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="a8794-230">Collections and Data Structures</span></span>](../../../standard/collections/index.md)
- [<span data-ttu-id="a8794-231">Seleccionar una clase de colección</span><span class="sxs-lookup"><span data-stu-id="a8794-231">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)
- [<span data-ttu-id="a8794-232">Comparaciones y ordenaciones en colecciones</span><span class="sxs-lookup"><span data-stu-id="a8794-232">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [<span data-ttu-id="a8794-233">Cuándo utilizar colecciones genéricas</span><span class="sxs-lookup"><span data-stu-id="a8794-233">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
