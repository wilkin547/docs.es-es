---
title: LINQ (Language Integrated Query)
description: "Obtenga información sobre cómo proporciona LINQ capacidades de consulta de nivel de lenguaje y una API para C# y VB que permite escribir código expresivo y declarativo."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 1478b5dc5844cef0abfea44eba88a12801d32bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="linq-language-integrated-query"></a>LINQ (Language Integrated Query)

## <a name="what-is-it"></a>¿Qué es?

LINQ proporciona capacidades de consulta de nivel de lenguaje y una API de [función de orden superior](https://en.wikipedia.org/wiki/Higher-order_function) para C# y VB que permite escribir código expresivo y declarativo.

Sintaxis de consulta de nivel de lenguaje:

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

Mismo ejemplo usando la API `IEnumerable<T>`:

```csharp
var linqExperts = programmers.Where(p => IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a>LINQ es expresivo

Imagine que tiene una lista de mascotas, pero desea convertirla en un diccionario en el que pueda tener acceso a cada mascota directamente por su valor `RFID`.

Código imperativo tradicional:

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

La intención de este código no es crear un nuevo `Dictionary<int, Pet>` y agregarle elementos por medio de un bucle, sino convertir una lista existente en un diccionario. LINQ conserva la intención, a diferencia del código imperativo.

Expresión LINQ equivalente:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

El código con LINQ tiene la ventaja de poner al mismo nivel la intención y el código cuando se razona como programador. Otra ventaja es la brevedad de código. Imagínese poder reducir gran parte de un código base en 1/3, como hemos visto más arriba. No estaría mal, ¿verdad?

## <a name="linq-providers-simplify-data-access"></a>Los proveedores LINQ simplifican el acceso a datos

Para una parte importante del software que conocemos, todo tiene que ver con el control de datos de algún origen (bases de datos, JSON, XML, etc.). A menudo, esto supone aprender una API nueva para cada origen de datos, y esto puede resultar tedioso. Para simplificar esta tarea, LINQ abstrae los elementos comunes del acceso a datos en una sintaxis de consulta que no varía sea cual sea el origen de datos que elija.

Veamos un ejemplo: buscar todos los elementos XML con un valor de atributo concreto.

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

Escribir código para recorrer manualmente el documento XML para realizar esta tarea sería bastante más complicado.

Interactuar con XML no es lo único que puede hacer con los proveedores LINQ. [LINQ to SQL](https://msdn.microsoft.com/library/bb386976.aspx) es un asignador relacional de objetos (ORM) bastante básico para una base de datos del servidor MSSQL. La biblioteca [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) proporciona una forma eficiente de recorrer documentos JSON mediante LINQ. Además, si no hay una biblioteca que haga lo que necesita, también puede [escribir su propio proveedor LINQ](https://msdn.microsoft.com/library/Bb546158.aspx).

## <a name="why-use-the-query-syntax"></a>¿Por qué usar la sintaxis de consulta?

Es una pregunta que surge con frecuencia. Después de todo, esto:

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

es mucho más conciso que esto:

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

¿No es la sintaxis de la API una manera más concisa de hacer la sintaxis de consulta?

No. Con la sintaxis de consulta se puede usar la cláusula **let**, que permite introducir y enlazar una variable dentro del ámbito de la expresión para usarla en las partes siguientes de la expresión. Es posible reproducir el mismo código con la sintaxis de la API, pero probablemente producirá un código difícil de leer.

Esto nos lleva a la pregunta: **¿debería usar la sintaxis de consulta solamente?**

La respuesta a esta pregunta es **sí** si...

*   el código base existente ya usa la sintaxis de consulta,
*   necesita establecer el ámbito de las variables en las consultas debido a su complejidad,
*   prefiere la sintaxis de consulta y esta no diverge de su código base.

La respuesta a esta pregunta es **no** si...

*   el código base existente ya usa la sintaxis de la API,
*   no necesita establecer el ámbito de las variables en las consultas,
*   prefiere la sintaxis de la API y esta no diverge de su código base.

## <a name="essential-samples"></a>Ejemplos básicos

Para obtener una lista realmente completa de ejemplos de LINQ, visite [101 ejemplos de LINQ](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).

Lo siguiente es una demostración rápida de algunas de las piezas básicas de LINQ. No pretende ser exhaustivo, ya que LINQ ofrece considerablemente más funcionalidad que la que se muestra aquí.

*   Las herramientas esenciales - `Where`, `Select`, y `Aggregate`:

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

// Summing then lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   Reducción de una lista de listas:

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   Unión entre dos conjuntos (con un comparador personalizado):

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
        return b.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   Intersección entre dos conjuntos:

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   Ordenación:

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   Por último, un ejemplo más avanzado: determinar si los valores de las propiedades de dos instancias del mismo tipo son iguales (tomado y modificado de [esta entrada de StackOverflow](http://stackoverflow.com/a/844855)):

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self != null && to != null)
    {
        var type = typeof(T);
        var ignoreList = new List<string>(ignore);

        // Selects the properties which have unequal values into a sequence of those properties.
        var unequalProperties = from pi in type.GetProperties(BindingFlags.Public | BindingFlags.Instance)
                                where !ignoreList.Contains(pi.Name)
                                let selfValue = type.GetProperty(pi.Name).GetValue(self, null)
                                let toValue = type.GetProperty(pi.Name).GetValue(to, null)
                                where selfValue != toValue && (selfValue == null || !selfValue.Equals(toValue))
                                select new { Prop = pi.Name, selfValue, toValue };
        return !unequalProperties.Any();
    }

    return self == to;
}
```

## <a name="plinq"></a>PLINQ

PLINQ, o Parallel LINQ, es un motor de ejecución en paralelo para expresiones de LINQ. En otras palabras, se pueden paralelizar las expresiones normales de LINQ de forma trivial en cualquier número de subprocesos. Para hacerlo, se emplea una llamada a `AsParallel()` delante de la expresión.

Considere el siguiente caso:

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

Este código repartirá `facebookUsers` en subprocesos del sistema según sea necesario, sumará el total de "Me gusta" de cada subproceso en paralelo, sumará los resultados calculados por cada subproceso y devolverá ese resultado en una bonita cadena.

En forma de diagrama:

![Diagrama de PLINQ](./media/using-linq/plinq-diagram.png)

Las tareas paralelizables vinculadas a la CPU que se pueden expresar fácilmente con LINQ (es decir, que son funciones puras y no tienen efectos secundarios) son un candidato excelente para PLINQ. Para tareas que _sí_ tienen efectos secundarios, considere el uso de [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx).

## <a name="further-resources"></a>Recursos adicionales:

*   [Ejemplos de LINQ 101](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   [Linqpad](https://www.linqpad.net/), un entorno de área de juegos y motor de consultas a bases de datos para C#/F#/VB
*   [EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), un libro electrónico para aprender cómo se implementa LINQ to Objects
