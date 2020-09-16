---
title: 'Información general de LINQ: .NET'
description: Language Integrated Query (LINQ) proporciona funcionalidades de consulta de nivel del lenguaje y una API de función de orden superior para C# y Visual Basic, que le permiten escribir código expresivo y declarativo.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 65370a2bd21e2474af4cb070bb8d82a167f10070
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555001"
---
# <a name="linq-overview"></a><span data-ttu-id="e749a-103">Información general de LINQ</span><span class="sxs-lookup"><span data-stu-id="e749a-103">LINQ overview</span></span>

<span data-ttu-id="e749a-104">Language Integrated Query (LINQ) proporciona funcionalidades de consulta de nivel del lenguaje y una API de [función de orden superior](https://en.wikipedia.org/wiki/Higher-order_function) para C# y Visual Basic, que le permiten escribir código expresivo y declarativo.</span><span class="sxs-lookup"><span data-stu-id="e749a-104">Language-Integrated Query (LINQ) provides language-level querying capabilities, and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic, that enable you to write expressive declarative code.</span></span>

## <a name="language-level-query-syntax"></a><span data-ttu-id="e749a-105">Sintaxis de consulta de nivel de lenguaje</span><span class="sxs-lookup"><span data-stu-id="e749a-105">Language-level query syntax</span></span>

<span data-ttu-id="e749a-106">Esta es la sintaxis de consulta de nivel de lenguaje:</span><span class="sxs-lookup"><span data-stu-id="e749a-106">This is the language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

```vb
Dim linqExperts = From p in programmers
                  Where p.IsNewToLINQ
                  Select New LINQExpert(p)
```

<span data-ttu-id="e749a-107">Este es el mismo ejemplo con la API `IEnumerable<T>`:</span><span class="sxs-lookup"><span data-stu-id="e749a-107">This is the same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="e749a-108">LINQ es expresivo</span><span class="sxs-lookup"><span data-stu-id="e749a-108">LINQ is expressive</span></span>

<span data-ttu-id="e749a-109">Imagine que tiene una lista de mascotas, pero desea convertirla en un diccionario en el que pueda tener acceso a cada mascota directamente por su valor `RFID`.</span><span class="sxs-lookup"><span data-stu-id="e749a-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="e749a-110">Este es código imperativo tradicional:</span><span class="sxs-lookup"><span data-stu-id="e749a-110">This is traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

<span data-ttu-id="e749a-111">La intención de este código no es crear un elemento `Dictionary<int, Pet>` y agregarle elementos por medio de un bucle, sino convertir una lista existente en un diccionario.</span><span class="sxs-lookup"><span data-stu-id="e749a-111">The intention behind the code isn't to create a new `Dictionary<int, Pet>` and add to it via a loop, it's to convert an existing list into a dictionary!</span></span> <span data-ttu-id="e749a-112">LINQ conserva la intención, a diferencia del código imperativo.</span><span class="sxs-lookup"><span data-stu-id="e749a-112">LINQ preserves the intention whereas the imperative code doesn't.</span></span>

<span data-ttu-id="e749a-113">Esta es la expresión LINQ equivalente:</span><span class="sxs-lookup"><span data-stu-id="e749a-113">This is the equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="e749a-114">El código con LINQ tiene la ventaja de poner al mismo nivel la intención y el código cuando se razona como programador.</span><span class="sxs-lookup"><span data-stu-id="e749a-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="e749a-115">Otra ventaja es la brevedad de código.</span><span class="sxs-lookup"><span data-stu-id="e749a-115">Another bonus is code brevity.</span></span> <span data-ttu-id="e749a-116">Imagínese poder reducir gran parte de un código base en 1/3, como hemos visto más arriba.</span><span class="sxs-lookup"><span data-stu-id="e749a-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="e749a-117">No estaría mal, ¿verdad?</span><span class="sxs-lookup"><span data-stu-id="e749a-117">Sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="e749a-118">Los proveedores LINQ simplifican el acceso a datos</span><span class="sxs-lookup"><span data-stu-id="e749a-118">LINQ providers simplify data access</span></span>

<span data-ttu-id="e749a-119">Para una parte importante del software existente, todo tiene que ver con el control de datos de algún origen (bases de datos, JSON, XML, etc.)</span><span class="sxs-lookup"><span data-stu-id="e749a-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, and so on).</span></span> <span data-ttu-id="e749a-120">A menudo, esto supone aprender una API nueva para cada origen de datos, y esto puede resultar tedioso.</span><span class="sxs-lookup"><span data-stu-id="e749a-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="e749a-121">Para simplificar esta tarea, LINQ abstrae los elementos comunes del acceso a datos en una sintaxis de consulta que no varía, con independencia del origen de datos que elija.</span><span class="sxs-lookup"><span data-stu-id="e749a-121">LINQ simplifies this by abstracting common elements of data access into a query syntax that looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="e749a-122">Esto busca todos los elementos XML con un valor de atributo concreto:</span><span class="sxs-lookup"><span data-stu-id="e749a-122">This finds all XML elements with a specific attribute value:</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function
```

<span data-ttu-id="e749a-123">Escribir código a fin de recorrer manualmente el documento XML para realizar esta tarea sería bastante más complicado.</span><span class="sxs-lookup"><span data-stu-id="e749a-123">Writing code to manually traverse the XML document to do this task would be far more challenging.</span></span>

<span data-ttu-id="e749a-124">Interactuar con XML no es lo único que puede hacer con los proveedores LINQ.</span><span class="sxs-lookup"><span data-stu-id="e749a-124">Interacting with XML isn't the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="e749a-125">[LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) es un asignador relacional de objetos (ORM) bastante básico para una base de datos del servidor MSSQL.</span><span class="sxs-lookup"><span data-stu-id="e749a-125">[Linq to SQL](../../framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="e749a-126">La biblioteca [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) proporciona una forma eficiente de recorrer documentos JSON mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="e749a-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="e749a-127">Además, si no hay una biblioteca que haga lo que necesita, también puede [escribir un proveedor LINQ propio](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="e749a-127">Furthermore, if there isn't a library that does what you need, you can also [write your own LINQ Provider](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="reasons-to-use-the-query-syntax"></a><span data-ttu-id="e749a-128">Motivos para usar la sintaxis de consulta</span><span class="sxs-lookup"><span data-stu-id="e749a-128">Reasons to use the query syntax</span></span>

<span data-ttu-id="e749a-129">¿Por qué usar la sintaxis de consulta?</span><span class="sxs-lookup"><span data-stu-id="e749a-129">Why use query syntax?</span></span> <span data-ttu-id="e749a-130">Es una pregunta que surge con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e749a-130">This is a question that often comes up.</span></span> <span data-ttu-id="e749a-131">Después de todo, el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e749a-131">After all, the following code:</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="e749a-132">es mucho más conciso que esto:</span><span class="sxs-lookup"><span data-stu-id="e749a-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

```vb
Dim filteredItems = From item In myItems
                    Where item.Foo
                    Select item
```

<span data-ttu-id="e749a-133">¿No es la sintaxis de la API una manera más concisa de la sintaxis de consulta?</span><span class="sxs-lookup"><span data-stu-id="e749a-133">Isn't the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="e749a-134">No.</span><span class="sxs-lookup"><span data-stu-id="e749a-134">No.</span></span> <span data-ttu-id="e749a-135">Con la sintaxis de consulta se puede usar la cláusula **let**, que permite introducir y enlazar una variable dentro del ámbito de la expresión para usarla en las partes siguientes de la expresión.</span><span class="sxs-lookup"><span data-stu-id="e749a-135">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="e749a-136">Se puede reproducir el mismo código con la sintaxis de la API, pero probablemente generará código difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="e749a-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code that's hard to read.</span></span>

<span data-ttu-id="e749a-137">Esto nos lleva a la pregunta: **¿debería usar la sintaxis de consulta solamente?**</span><span class="sxs-lookup"><span data-stu-id="e749a-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="e749a-138">La respuesta a esta pregunta es **sí** si:</span><span class="sxs-lookup"><span data-stu-id="e749a-138">The answer to this question is **yes** if:</span></span>

- <span data-ttu-id="e749a-139">El código base existente ya usa la sintaxis de consulta.</span><span class="sxs-lookup"><span data-stu-id="e749a-139">Your existing codebase already uses the query syntax.</span></span>
- <span data-ttu-id="e749a-140">Es necesario establecer el ámbito de las variables en las consultas debido a su complejidad.</span><span class="sxs-lookup"><span data-stu-id="e749a-140">You need to scope variables within your queries because of complexity.</span></span>
- <span data-ttu-id="e749a-141">Prefiere la sintaxis de consulta y esta no diverge del código base.</span><span class="sxs-lookup"><span data-stu-id="e749a-141">You prefer the query syntax and it won't distract from your codebase.</span></span>

<span data-ttu-id="e749a-142">La respuesta a esta pregunta es **no** si...</span><span class="sxs-lookup"><span data-stu-id="e749a-142">The answer to this question is **no** if...</span></span>

- <span data-ttu-id="e749a-143">el código base existente ya usa la sintaxis de la API,</span><span class="sxs-lookup"><span data-stu-id="e749a-143">Your existing codebase already uses the API syntax</span></span>
- <span data-ttu-id="e749a-144">no necesita establecer el ámbito de las variables en las consultas,</span><span class="sxs-lookup"><span data-stu-id="e749a-144">You have no need to scope variables within your queries</span></span>
- <span data-ttu-id="e749a-145">prefiere la sintaxis de la API y esta no diverge del código base</span><span class="sxs-lookup"><span data-stu-id="e749a-145">You prefer the API syntax and it won't distract from your codebase</span></span>

## <a name="essential-linq"></a><span data-ttu-id="e749a-146">LINQ básico</span><span class="sxs-lookup"><span data-stu-id="e749a-146">Essential LINQ</span></span>

<span data-ttu-id="e749a-147">Para obtener una lista realmente completa de ejemplos de LINQ, visite [101 ejemplos de LINQ](/samples/dotnet/try-samples/101-linq-samples/).</span><span class="sxs-lookup"><span data-stu-id="e749a-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/).</span></span>

<span data-ttu-id="e749a-148">Los ejemplos siguientes son una demostración rápida de algunas de las piezas básicas de LINQ.</span><span class="sxs-lookup"><span data-stu-id="e749a-148">The following examples are a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="e749a-149">No pretende ser exhaustivo, ya que LINQ ofrece más funcionalidad que la que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="e749a-149">This is in no way comprehensive, as LINQ provides more functionality than what is showcased here.</span></span>

### <a name="the-bread-and-butter---where-select-and-aggregate"></a><span data-ttu-id="e749a-150">Las herramientas esenciales: `Where`, `Select`, y `Aggregate`</span><span class="sxs-lookup"><span data-stu-id="e749a-150">The bread and butter - `Where`, `Select`, and `Aggregate`</span></span>

```csharp
// Filtering a list.
var germanShepherds = dogs.Where(dog => dog.Breed == DogBreed.GermanShepherd);

// Using the query syntax.
var queryGermanShepherds = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepherd
                          select dog;

// Mapping a list from type A to type B.
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax.
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings.
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

```vb
' Filtering a list.
Dim germanShepherds = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepherd)

' Using the query syntax.
Dim queryGermanShepherds = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepherd
                          Select dog

' Mapping a list from type A to type B.
Dim cats = dogs.Select(Function(dog) dog.TurnIntoACat())

' Using the query syntax.
Dim queryCats = From dog In dogs
                Select dog.TurnIntoACat()

' Summing the lengths of a set of strings.
Dim seed As Integer = 0
Dim sumOfStrings As Integer = strings.Aggregate(seed, Function(s1, s2) s1.Length + s2.Length)
```

### <a name="flattening-a-list-of-lists"></a><span data-ttu-id="e749a-151">Acoplamiento de una lista de listas</span><span class="sxs-lookup"><span data-stu-id="e749a-151">Flattening a list of lists</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a><span data-ttu-id="e749a-152">Unión entre dos conjuntos (con un comparador personalizado)</span><span class="sxs-lookup"><span data-stu-id="e749a-152">Union between two sets (with custom comparator)</span></span>

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
        // Default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}
...

// Gets all the short-haired dogs between two different kennels.
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());

```

```vb
Public Class DogHairLengthComparer
  Inherits IEqualityComparer(Of Dog)

  Public Function Equals(a As Dog,b As Dog) As Boolean
      If a Is Nothing AndAlso b Is Nothing Then
          Return True
      ElseIf (a Is Nothing AndAlso b IsNot Nothing) OrElse (a IsNot Nothing AndAlso b Is Nothing) Then
          Return False
      Else
          Return a.HairLengthType = b.HairLengthType
      End If
  End Function

  Public Function GetHashCode(d As Dog) As Integer
      ' Default hashcode is enough here, as these are simple objects.
      Return d.GetHashCode()
  End Function
End Class

...

' Gets all the short-haired dogs between two different kennels.
Dim allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, New DogHairLengthComparer())
```

### <a name="intersection-between-two-sets"></a><span data-ttu-id="e749a-153">Intersección entre dos conjuntos</span><span class="sxs-lookup"><span data-stu-id="e749a-153">Intersection between two sets</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

```vb
' Gets the volunteers who spend share time with two humane societies.
Dim volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     New VolunteerTimeComparer())
```

### <a name="ordering"></a><span data-ttu-id="e749a-154">Ordenación</span><span class="sxs-lookup"><span data-stu-id="e749a-154">Ordering</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

```vb
' Get driving directions, ordering by if it's toll-free before estimated driving time.
Dim results = DirectionsProcessor.GetDirections(start, end).
                OrderBy(Function(direction) direction.HasNoTolls).
                ThenBy(Function(direction) direction.EstimatedTime)
```

### <a name="equality-of-instance-properties"></a><span data-ttu-id="e749a-155">Igualdad de las propiedades de instancia</span><span class="sxs-lookup"><span data-stu-id="e749a-155">Equality of instance properties</span></span>

<span data-ttu-id="e749a-156">Por último, un ejemplo más avanzado: determinar si los valores de las propiedades de dos instancias del mismo tipo son iguales (tomado y modificado de [esta entrada de StackOverflow](https://stackoverflow.com/a/844855)):</span><span class="sxs-lookup"><span data-stu-id="e749a-156">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

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

```vb
<System.Runtime.CompilerServices.Extension()>
Public Function PublicInstancePropertiesEqual(Of T As Class)(self As T, [to] As T, ParamArray ignore As String()) As Boolean
    If self Is Nothing OrElse [to] Is Nothing Then
        Return self Is [to]
    End If

    ' Selects the properties which have unequal values into a sequence of those properties.
    Dim unequalProperties = From [property] In GetType(T).GetProperties(BindingFlags.Public Or BindingFlags.Instance)
                            Where Not ignore.Contains([property].Name)
                            Let selfValue = [property].GetValue(self, Nothing)
                            Let toValue = [property].GetValue([to], Nothing)
                            Where Not Equals(selfValue, toValue) Select [property]
    Return Not unequalProperties.Any()
End Function
```

## <a name="plinq"></a><span data-ttu-id="e749a-157">PLINQ</span><span class="sxs-lookup"><span data-stu-id="e749a-157">PLINQ</span></span>

<span data-ttu-id="e749a-158">PLINQ, o Parallel LINQ, es un motor de ejecución en paralelo para expresiones de LINQ.</span><span class="sxs-lookup"><span data-stu-id="e749a-158">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="e749a-159">En otras palabras, se puede paralelizar una expresión normal de LINQ de forma trivial en cualquier número de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e749a-159">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="e749a-160">Para hacerlo, se emplea una llamada a `AsParallel()` delante de la expresión.</span><span class="sxs-lookup"><span data-stu-id="e749a-160">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="e749a-161">Tenga en cuenta lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e749a-161">Consider the following:</span></span>

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

```vb
Public Shared GetAllFacebookUserLikesMessage(facebookUsers As IEnumerable(Of FacebookUser)) As String
{
    Dim seed As UInt64 = 0

    Dim threadAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim threadResultAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim resultSelector As Func(Of Uint64, string) = Function(total) $"Facebook has {total} likes!"

    Return facebookUsers.AsParallel().
                        Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector)
}
```

<span data-ttu-id="e749a-162">Este código repartirá `facebookUsers` en subprocesos del sistema según sea necesario, sumará el total de "Me gusta" de cada subproceso en paralelo, sumará los resultados calculados por cada subproceso y devolverá ese resultado en una bonita cadena.</span><span class="sxs-lookup"><span data-stu-id="e749a-162">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="e749a-163">En forma de diagrama:</span><span class="sxs-lookup"><span data-stu-id="e749a-163">In diagram form:</span></span>

![Diagrama de PLINQ](media/index/plinq-diagram.png)

<span data-ttu-id="e749a-165">Las tareas paralelizables vinculadas a la CPU que se pueden expresar fácilmente con LINQ (es decir, que son funciones puras y no tienen efectos secundarios) son un candidato excelente para PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e749a-165">Parallelizable CPU-bound jobs that can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="e749a-166">Para tareas que _sí_ tienen efectos secundarios, considere el uso de [la Biblioteca TLP](../parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="e749a-166">For jobs that _do_ have a side effect, consider using the [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="e749a-167">Más recursos</span><span class="sxs-lookup"><span data-stu-id="e749a-167">More resources</span></span>

* [<span data-ttu-id="e749a-168">Ejemplos de LINQ 101</span><span class="sxs-lookup"><span data-stu-id="e749a-168">101 LINQ Samples</span></span>](/samples/dotnet/try-samples/101-linq-samples/)
* <span data-ttu-id="e749a-169">[Linqpad](https://www.linqpad.net/), un entorno de área de juegos y motor de consultas a bases de datos para C#/F#/Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e749a-169">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="e749a-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un libro electrónico para aprender cómo se implementa LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="e749a-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
