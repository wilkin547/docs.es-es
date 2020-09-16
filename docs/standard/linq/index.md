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
# <a name="linq-overview"></a>Información general de LINQ

Language Integrated Query (LINQ) proporciona funcionalidades de consulta de nivel del lenguaje y una API de [función de orden superior](https://en.wikipedia.org/wiki/Higher-order_function) para C# y Visual Basic, que le permiten escribir código expresivo y declarativo.

## <a name="language-level-query-syntax"></a>Sintaxis de consulta de nivel de lenguaje

Esta es la sintaxis de consulta de nivel de lenguaje:

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

Este es el mismo ejemplo con la API `IEnumerable<T>`:

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a>LINQ es expresivo

Imagine que tiene una lista de mascotas, pero desea convertirla en un diccionario en el que pueda tener acceso a cada mascota directamente por su valor `RFID`.

Este es código imperativo tradicional:

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

La intención de este código no es crear un elemento `Dictionary<int, Pet>` y agregarle elementos por medio de un bucle, sino convertir una lista existente en un diccionario. LINQ conserva la intención, a diferencia del código imperativo.

Esta es la expresión LINQ equivalente:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

El código con LINQ tiene la ventaja de poner al mismo nivel la intención y el código cuando se razona como programador. Otra ventaja es la brevedad de código. Imagínese poder reducir gran parte de un código base en 1/3, como hemos visto más arriba. No estaría mal, ¿verdad?

## <a name="linq-providers-simplify-data-access"></a>Los proveedores LINQ simplifican el acceso a datos

Para una parte importante del software existente, todo tiene que ver con el control de datos de algún origen (bases de datos, JSON, XML, etc.) A menudo, esto supone aprender una API nueva para cada origen de datos, y esto puede resultar tedioso. Para simplificar esta tarea, LINQ abstrae los elementos comunes del acceso a datos en una sintaxis de consulta que no varía, con independencia del origen de datos que elija.

Esto busca todos los elementos XML con un valor de atributo concreto:

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

Escribir código a fin de recorrer manualmente el documento XML para realizar esta tarea sería bastante más complicado.

Interactuar con XML no es lo único que puede hacer con los proveedores LINQ. [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) es un asignador relacional de objetos (ORM) bastante básico para una base de datos del servidor MSSQL. La biblioteca [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) proporciona una forma eficiente de recorrer documentos JSON mediante LINQ. Además, si no hay una biblioteca que haga lo que necesita, también puede [escribir un proveedor LINQ propio](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).

## <a name="reasons-to-use-the-query-syntax"></a>Motivos para usar la sintaxis de consulta

¿Por qué usar la sintaxis de consulta? Es una pregunta que surge con frecuencia. Después de todo, el código siguiente:

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

es mucho más conciso que esto:

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

¿No es la sintaxis de la API una manera más concisa de la sintaxis de consulta?

No. Con la sintaxis de consulta se puede usar la cláusula **let**, que permite introducir y enlazar una variable dentro del ámbito de la expresión para usarla en las partes siguientes de la expresión. Se puede reproducir el mismo código con la sintaxis de la API, pero probablemente generará código difícil de leer.

Esto nos lleva a la pregunta: **¿debería usar la sintaxis de consulta solamente?**

La respuesta a esta pregunta es **sí** si:

- El código base existente ya usa la sintaxis de consulta.
- Es necesario establecer el ámbito de las variables en las consultas debido a su complejidad.
- Prefiere la sintaxis de consulta y esta no diverge del código base.

La respuesta a esta pregunta es **no** si...

- el código base existente ya usa la sintaxis de la API,
- no necesita establecer el ámbito de las variables en las consultas,
- prefiere la sintaxis de la API y esta no diverge del código base

## <a name="essential-linq"></a>LINQ básico

Para obtener una lista realmente completa de ejemplos de LINQ, visite [101 ejemplos de LINQ](/samples/dotnet/try-samples/101-linq-samples/).

Los ejemplos siguientes son una demostración rápida de algunas de las piezas básicas de LINQ. No pretende ser exhaustivo, ya que LINQ ofrece más funcionalidad que la que se muestra aquí.

### <a name="the-bread-and-butter---where-select-and-aggregate"></a>Las herramientas esenciales: `Where`, `Select`, y `Aggregate`

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

### <a name="flattening-a-list-of-lists"></a>Acoplamiento de una lista de listas

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a>Unión entre dos conjuntos (con un comparador personalizado)

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

### <a name="intersection-between-two-sets"></a>Intersección entre dos conjuntos

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

### <a name="ordering"></a>Ordenación

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

### <a name="equality-of-instance-properties"></a>Igualdad de las propiedades de instancia

Por último, un ejemplo más avanzado: determinar si los valores de las propiedades de dos instancias del mismo tipo son iguales (tomado y modificado de [esta entrada de StackOverflow](https://stackoverflow.com/a/844855)):

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

## <a name="plinq"></a>PLINQ

PLINQ, o Parallel LINQ, es un motor de ejecución en paralelo para expresiones de LINQ. En otras palabras, se puede paralelizar una expresión normal de LINQ de forma trivial en cualquier número de subprocesos. Para hacerlo, se emplea una llamada a `AsParallel()` delante de la expresión.

Tenga en cuenta lo siguiente.

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

Este código repartirá `facebookUsers` en subprocesos del sistema según sea necesario, sumará el total de "Me gusta" de cada subproceso en paralelo, sumará los resultados calculados por cada subproceso y devolverá ese resultado en una bonita cadena.

En forma de diagrama:

![Diagrama de PLINQ](media/index/plinq-diagram.png)

Las tareas paralelizables vinculadas a la CPU que se pueden expresar fácilmente con LINQ (es decir, que son funciones puras y no tienen efectos secundarios) son un candidato excelente para PLINQ. Para tareas que _sí_ tienen efectos secundarios, considere el uso de [la Biblioteca TLP](../parallel-programming/task-parallel-library-tpl.md).

## <a name="more-resources"></a>Más recursos

* [Ejemplos de LINQ 101](/samples/dotnet/try-samples/101-linq-samples/)
* [Linqpad](https://www.linqpad.net/), un entorno de área de juegos y motor de consultas a bases de datos para C#/F#/Visual Basic
* [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un libro electrónico para aprender cómo se implementa LINQ to Objects
