---
title: LINQ (Language Integrated Query)
description: Obtenga información sobre cómo proporciona LINQ capacidades de consulta de nivel de lenguaje y una API para C# y VB que permite escribir código expresivo y declarativo.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 4e6e361666b6b6ae36b7d4bf02af55a379c8e16e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999800"
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="3eb16-103">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="3eb16-103">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="3eb16-104">¿Qué es?</span><span class="sxs-lookup"><span data-stu-id="3eb16-104">What is it?</span></span>

<span data-ttu-id="3eb16-105">LINQ proporciona capacidades de consulta de nivel de lenguaje y una API de [función de orden superior](https://en.wikipedia.org/wiki/Higher-order_function) para C# y VB que permite escribir código expresivo y declarativo.</span><span class="sxs-lookup"><span data-stu-id="3eb16-105">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and VB as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="3eb16-106">Sintaxis de consulta de nivel de lenguaje:</span><span class="sxs-lookup"><span data-stu-id="3eb16-106">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

<span data-ttu-id="3eb16-107">Mismo ejemplo usando la API `IEnumerable<T>`:</span><span class="sxs-lookup"><span data-stu-id="3eb16-107">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a><span data-ttu-id="3eb16-108">LINQ es expresivo</span><span class="sxs-lookup"><span data-stu-id="3eb16-108">LINQ is Expressive</span></span>

<span data-ttu-id="3eb16-109">Imagine que tiene una lista de mascotas, pero desea convertirla en un diccionario en el que pueda tener acceso a cada mascota directamente por su valor `RFID`.</span><span class="sxs-lookup"><span data-stu-id="3eb16-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="3eb16-110">Código imperativo tradicional:</span><span class="sxs-lookup"><span data-stu-id="3eb16-110">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

<span data-ttu-id="3eb16-111">La intención de este código no es crear un nuevo `Dictionary<int, Pet>` y agregarle elementos por medio de un bucle, sino convertir una lista existente en un diccionario.</span><span class="sxs-lookup"><span data-stu-id="3eb16-111">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="3eb16-112">LINQ conserva la intención, a diferencia del código imperativo.</span><span class="sxs-lookup"><span data-stu-id="3eb16-112">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="3eb16-113">Expresión LINQ equivalente:</span><span class="sxs-lookup"><span data-stu-id="3eb16-113">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

<span data-ttu-id="3eb16-114">El código con LINQ tiene la ventaja de poner al mismo nivel la intención y el código cuando se razona como programador.</span><span class="sxs-lookup"><span data-stu-id="3eb16-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="3eb16-115">Otra ventaja es la brevedad de código.</span><span class="sxs-lookup"><span data-stu-id="3eb16-115">Another bonus is code brevity.</span></span> <span data-ttu-id="3eb16-116">Imagínese poder reducir gran parte de un código base en 1/3, como hemos visto más arriba.</span><span class="sxs-lookup"><span data-stu-id="3eb16-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="3eb16-117">No estaría mal, ¿verdad?</span><span class="sxs-lookup"><span data-stu-id="3eb16-117">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="3eb16-118">Los proveedores LINQ simplifican el acceso a datos</span><span class="sxs-lookup"><span data-stu-id="3eb16-118">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="3eb16-119">Para una parte importante del software que conocemos, todo tiene que ver con el control de datos de algún origen (bases de datos, JSON, XML, etc.).</span><span class="sxs-lookup"><span data-stu-id="3eb16-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="3eb16-120">A menudo, esto supone aprender una API nueva para cada origen de datos, y esto puede resultar tedioso.</span><span class="sxs-lookup"><span data-stu-id="3eb16-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="3eb16-121">Para simplificar esta tarea, LINQ abstrae los elementos comunes del acceso a datos en una sintaxis de consulta que no varía sea cual sea el origen de datos que elija.</span><span class="sxs-lookup"><span data-stu-id="3eb16-121">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="3eb16-122">Veamos un ejemplo: buscar todos los elementos XML con un valor de atributo concreto.</span><span class="sxs-lookup"><span data-stu-id="3eb16-122">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

<span data-ttu-id="3eb16-123">Escribir código para recorrer manualmente el documento XML para realizar esta tarea sería bastante más complicado.</span><span class="sxs-lookup"><span data-stu-id="3eb16-123">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="3eb16-124">Interactuar con XML no es lo único que puede hacer con los proveedores LINQ.</span><span class="sxs-lookup"><span data-stu-id="3eb16-124">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="3eb16-125">[LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) es un asignador relacional de objetos (ORM) bastante básico para una base de datos del servidor MSSQL.</span><span class="sxs-lookup"><span data-stu-id="3eb16-125">[Linq to SQL](../../docs/framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="3eb16-126">La biblioteca [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) proporciona una forma eficiente de recorrer documentos JSON mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="3eb16-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="3eb16-127">Además, si no hay una biblioteca que haga lo que necesita, también puede [escribir su propio proveedor LINQ](https://msdn.microsoft.com/library/Bb546158.aspx).</span><span class="sxs-lookup"><span data-stu-id="3eb16-127">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://msdn.microsoft.com/library/Bb546158.aspx)!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="3eb16-128">¿Por qué usar la sintaxis de consulta?</span><span class="sxs-lookup"><span data-stu-id="3eb16-128">Why Use the Query Syntax?</span></span>

<span data-ttu-id="3eb16-129">Es una pregunta que surge con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="3eb16-129">This is a question which often comes up.</span></span> <span data-ttu-id="3eb16-130">Después de todo, esto:</span><span class="sxs-lookup"><span data-stu-id="3eb16-130">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

<span data-ttu-id="3eb16-131">es mucho más conciso que esto:</span><span class="sxs-lookup"><span data-stu-id="3eb16-131">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

<span data-ttu-id="3eb16-132">¿No es la sintaxis de la API una manera más concisa de hacer la sintaxis de consulta?</span><span class="sxs-lookup"><span data-stu-id="3eb16-132">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="3eb16-133">No.</span><span class="sxs-lookup"><span data-stu-id="3eb16-133">No.</span></span> <span data-ttu-id="3eb16-134">Con la sintaxis de consulta se puede usar la cláusula **let**, que permite introducir y enlazar una variable dentro del ámbito de la expresión para usarla en las partes siguientes de la expresión.</span><span class="sxs-lookup"><span data-stu-id="3eb16-134">The query syntax allows for the use the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="3eb16-135">Es posible reproducir el mismo código con la sintaxis de la API, pero probablemente producirá un código difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="3eb16-135">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="3eb16-136">Esto nos lleva a la pregunta: **¿debería usar la sintaxis de consulta solamente?**</span><span class="sxs-lookup"><span data-stu-id="3eb16-136">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="3eb16-137">La respuesta a esta pregunta es **sí** si...</span><span class="sxs-lookup"><span data-stu-id="3eb16-137">The answer to this question is **yes** if...</span></span>

*   <span data-ttu-id="3eb16-138">el código base existente ya usa la sintaxis de consulta,</span><span class="sxs-lookup"><span data-stu-id="3eb16-138">Your existing codebase already uses the query syntax</span></span>
*   <span data-ttu-id="3eb16-139">necesita establecer el ámbito de las variables en las consultas debido a su complejidad,</span><span class="sxs-lookup"><span data-stu-id="3eb16-139">You need to scope variables within your queries due to complexity</span></span>
*   <span data-ttu-id="3eb16-140">prefiere la sintaxis de consulta y esta no diverge de su código base.</span><span class="sxs-lookup"><span data-stu-id="3eb16-140">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="3eb16-141">La respuesta a esta pregunta es **no** si...</span><span class="sxs-lookup"><span data-stu-id="3eb16-141">The answer to this question is **no** if...</span></span>

*   <span data-ttu-id="3eb16-142">el código base existente ya usa la sintaxis de la API,</span><span class="sxs-lookup"><span data-stu-id="3eb16-142">Your existing codebase already uses the API syntax</span></span>
*   <span data-ttu-id="3eb16-143">no necesita establecer el ámbito de las variables en las consultas,</span><span class="sxs-lookup"><span data-stu-id="3eb16-143">You have no need to scope variables within your queries</span></span>
*   <span data-ttu-id="3eb16-144">prefiere la sintaxis de la API y esta no diverge de su código base.</span><span class="sxs-lookup"><span data-stu-id="3eb16-144">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="3eb16-145">Ejemplos básicos</span><span class="sxs-lookup"><span data-stu-id="3eb16-145">Essential Samples</span></span>

<span data-ttu-id="3eb16-146">Para obtener una lista realmente completa de ejemplos de LINQ, visite [101 ejemplos de LINQ](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span><span class="sxs-lookup"><span data-stu-id="3eb16-146">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="3eb16-147">Lo siguiente es una demostración rápida de algunas de las piezas básicas de LINQ.</span><span class="sxs-lookup"><span data-stu-id="3eb16-147">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="3eb16-148">No pretende ser exhaustivo, ya que LINQ ofrece considerablemente más funcionalidad que la que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="3eb16-148">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

*   <span data-ttu-id="3eb16-149">Las herramientas esenciales - `Where`, `Select`, y `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="3eb16-149">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   <span data-ttu-id="3eb16-150">Reducción de una lista de listas:</span><span class="sxs-lookup"><span data-stu-id="3eb16-150">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   <span data-ttu-id="3eb16-151">Unión entre dos conjuntos (con un comparador personalizado):</span><span class="sxs-lookup"><span data-stu-id="3eb16-151">Union between two sets (with custom comparator):</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   <span data-ttu-id="3eb16-152">Intersección entre dos conjuntos:</span><span class="sxs-lookup"><span data-stu-id="3eb16-152">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   <span data-ttu-id="3eb16-153">Ordenación:</span><span class="sxs-lookup"><span data-stu-id="3eb16-153">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   <span data-ttu-id="3eb16-154">Por último, un ejemplo más avanzado: determinar si los valores de las propiedades de dos instancias del mismo tipo son iguales (tomado y modificado de [esta entrada de StackOverflow](http://stackoverflow.com/a/844855)):</span><span class="sxs-lookup"><span data-stu-id="3eb16-154">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](http://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self == null || to == null)
    {
        return self == to;
    }
    
    // Selects the properties which have unequal values into a sequence of those properties.
    var unequalProperties = from property in typeof(T).GetProperties(BindingFlags.Public | BindingFlags.Instance)
                            where !ignore.Contains(property.Name)
                            let selfValue = property.GetValue(self, null)
                            let toValue = property.GetValue(to, null)
                            where !Equals(selfValue, toValue)
                            select property;
    return !unequalProperties.Any();
}
```

## <a name="plinq"></a><span data-ttu-id="3eb16-155">PLINQ</span><span class="sxs-lookup"><span data-stu-id="3eb16-155">PLINQ</span></span>

<span data-ttu-id="3eb16-156">PLINQ, o Parallel LINQ, es un motor de ejecución en paralelo para expresiones de LINQ.</span><span class="sxs-lookup"><span data-stu-id="3eb16-156">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="3eb16-157">En otras palabras, se pueden paralelizar las expresiones normales de LINQ de forma trivial en cualquier número de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3eb16-157">In other words, a regular LINQ expressions can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="3eb16-158">Para hacerlo, se emplea una llamada a `AsParallel()` delante de la expresión.</span><span class="sxs-lookup"><span data-stu-id="3eb16-158">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="3eb16-159">Considere el siguiente caso:</span><span class="sxs-lookup"><span data-stu-id="3eb16-159">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

<span data-ttu-id="3eb16-160">Este código repartirá `facebookUsers` en subprocesos del sistema según sea necesario, sumará el total de "Me gusta" de cada subproceso en paralelo, sumará los resultados calculados por cada subproceso y devolverá ese resultado en una bonita cadena.</span><span class="sxs-lookup"><span data-stu-id="3eb16-160">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="3eb16-161">En forma de diagrama:</span><span class="sxs-lookup"><span data-stu-id="3eb16-161">In diagram form:</span></span>

![Diagrama de PLINQ](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="3eb16-163">Las tareas paralelizables vinculadas a la CPU que se pueden expresar fácilmente con LINQ (es decir, que son funciones puras y no tienen efectos secundarios) son un candidato excelente para PLINQ.</span><span class="sxs-lookup"><span data-stu-id="3eb16-163">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="3eb16-164">Para tareas que _sí_ tienen efectos secundarios, considere el uso de [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="3eb16-164">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="further-resources"></a><span data-ttu-id="3eb16-165">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="3eb16-165">Further Resources:</span></span>

*   [<span data-ttu-id="3eb16-166">Ejemplos de LINQ 101</span><span class="sxs-lookup"><span data-stu-id="3eb16-166">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   <span data-ttu-id="3eb16-167">[Linqpad](https://www.linqpad.net/), un entorno de área de juegos y motor de consultas a bases de datos para C#/F#/VB</span><span class="sxs-lookup"><span data-stu-id="3eb16-167">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/VB</span></span>
*   <span data-ttu-id="3eb16-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un libro electrónico para aprender cómo se implementa LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="3eb16-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
