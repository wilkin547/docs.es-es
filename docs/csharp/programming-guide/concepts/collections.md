---
title: Colecciones (C#)
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: 30aa3e34f362f34fc601f90ee61613acd6e4bc68
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201130"
---
# <a name="collections-c"></a>Colecciones (C#)

Para muchas aplicaciones, puede que desee crear y administrar grupos de objetos relacionados. Existen dos formas de agrupar objetos: mediante la creación de matrices de objetos y con la creación de colecciones de objetos.

Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados. Para obtener información sobre las matrices, vea [Matrices](../arrays/index.md).

Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. A diferencia de las matrices, el grupo de objetos con el que trabaja puede aumentar y reducirse de manera dinámica a medida que cambian las necesidades de la aplicación. Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.

Una colección es una clase, por lo que debe declarar una instancia de la clase para poder agregar elementos a dicha colección.

Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>. Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella. Cuando recupera un elemento de una colección genérica, no tiene que determinar su tipo de datos ni convertirlo.

> [!NOTE]
> Para los ejemplos de este tema, incluya las directivas [using](../../language-reference/keywords/using-directive.md) para los espacios de nombres `System.Collections.Generic` y `System.Linq`.

 **En este tema**

- [Uso de una colección Simple](#BKMK_SimpleCollection)

- [Tipos de colecciones](#BKMK_KindsOfCollections)

  - [Clases System.Collections.Generic](#BKMK_Generic)

  - [Clases System.Collections.Concurrent](#BKMK_Concurrent)

  - [Clases System.Collections](#BKMK_Collections)

- [Implementación de una colección de pares de clave/valor](#BKMK_KeyValuePairs)

- [Uso de LINQ para tener acceso a una colección](#BKMK_LINQ)

- [Ordenar una colección](#BKMK_Sorting)

- [Definición de una colección personalizada](#BKMK_CustomCollection)

- [Iteradores](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Uso de una colección Simple

Los ejemplos de esta sección usan la clase genérica <xref:System.Collections.Generic.List%601>, que le permite trabajar con una lista de objetos fuertemente tipados.

En el ejemplo siguiente se crea una lista de cadenas y luego se recorren en iteración mediante una instrucción [foreach](../../language-reference/keywords/foreach-in.md).

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

Si el contenido de una colección se conoce de antemano, puede usar un *inicializador de colección* para inicializar la colección. Para obtener más información, vea [Inicializadores de objeto y colección](../classes-and-structs/object-and-collection-initializers.md).

El ejemplo siguiente es el mismo que el ejemplo anterior, excepto que se usa un inicializador de colección para agregar elementos a la colección.

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

Puede usar una instrucción [for](../../language-reference/keywords/for.md) en lugar de una instrucción `foreach` para recorrer en iteración una colección. Esto se consigue con el acceso a los elementos de la colección mediante la posición de índice. El índice de los elementos comienza en 0 y termina en el número de elementos menos 1.

El ejemplo siguiente recorre en iteración los elementos de una colección mediante `for` en lugar de `foreach`.

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

El ejemplo siguiente quita un elemento de la colección especificando el objeto que se quitará.

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

El ejemplo siguiente quita elementos de una lista genérica. En lugar de una instrucción `foreach`, se usa una instrucción [for](../../language-reference/keywords/for.md) que procesa una iteración en orden descendente. Esto es porque el método <xref:System.Collections.Generic.List%601.RemoveAt%2A> hace que los elementos después de un elemento quitado tengan un valor de índice inferior.

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

Para el tipo de elementos de <xref:System.Collections.Generic.List%601>, también puede definir su propia clase. En el ejemplo siguiente, la clase `Galaxy` que usa <xref:System.Collections.Generic.List%601> se define en el código.

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

## <a name="kinds-of-collections"></a>Tipos de colecciones

.NET Framework proporciona muchas colecciones comunes. Cada tipo de colección está diseñado para un fin específico.

En esta sección se describen algunas de las clases de colecciones comunes:

- Clases <xref:System.Collections.Generic>

- Clases <xref:System.Collections.Concurrent>

- Clases <xref:System.Collections>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>Clases System.Collections.Generic

Puede crear una colección genérica mediante una de las clases del espacio de nombres <xref:System.Collections.Generic>. Una colección genérica es útil cuando todos los elementos de la colección tienen el mismo tipo. Una colección genérica exige el establecimiento de fuertes tipos al permitir agregar solo los tipos de datos deseados.

En la tabla siguiente se enumeran algunas de las clases usadas con frecuencia del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>:

|Clase|Descripción|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Representa una colección de pares de clave y valor que se organizan según la clave.|
|<xref:System.Collections.Generic.List%601>|Representa una lista de objetos a los que puede tener acceso el índice. Proporciona métodos para buscar, ordenar y modificar listas.|
|<xref:System.Collections.Generic.Queue%601>|Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).|
|<xref:System.Collections.Generic.SortedList%602>|Representa una colección de pares clave-valor que se ordenan por claves según la implementación de <xref:System.Collections.Generic.IComparer%601> asociada.|
|<xref:System.Collections.Generic.Stack%601>|Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).|

Para obtener más información, vea [Tipos de colección utilizados normalmente](../../../standard/collections/commonly-used-collection-types.md), [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md) y <xref:System.Collections.Generic>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>Clases System.Collections.Concurrent

En .NET Framework 4 o posterior, las colecciones del espacio de nombres <xref:System.Collections.Concurrent> proporcionan operaciones eficaces y seguras para subprocesos con el fin de obtener acceso a los elementos de la colección desde varios subprocesos.

Las clases del espacio de nombres <xref:System.Collections.Concurrent> deben usarse en lugar de los tipos correspondientes de los espacios de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> y <xref:System.Collections?displayProperty=nameWithType> cada vez que varios subprocesos tengan acceso de manera simultánea a la colección. Para obtener más información, vea [Colecciones seguras para subprocesos](../../../standard/collections/thread-safe/index.md) y <xref:System.Collections.Concurrent>.

Algunas clases incluidas en el espacio de nombres <xref:System.Collections.Concurrent> son <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a>Clases System.Collections

Las clases del espacio de nombres <xref:System.Collections?displayProperty=nameWithType> no almacenan los elementos como objetos de tipo específico, sino como objetos del tipo `Object`.

Siempre que sea posible, debe usar las colecciones genéricas del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> o del espacio de nombres <xref:System.Collections.Concurrent> en lugar de los tipos heredados del espacio de nombres `System.Collections`.

En la siguiente tabla se enumeran algunas de las clases usadas con frecuencia en el espacio de nombres `System.Collections`:

|Clase|Descripción|
|---|---|
|<xref:System.Collections.ArrayList>|Representa una matriz cuyo tamaño aumenta dinámicamente cuando es necesario.|
|<xref:System.Collections.Hashtable>|Representa una colección de pares de clave y valor que se organizan por código hash de la clave.|
|<xref:System.Collections.Queue>|Representa una colección de objetos de primeras entradas, primeras salidas (FIFO).|
|<xref:System.Collections.Stack>|Representa una colección de objetos de últimas entradas, primeras salidas (LIFO).|

El espacio de nombres <xref:System.Collections.Specialized> proporciona clases de colección especializadas y fuertemente tipadas como, por ejemplo, colecciones de solo cadena y diccionarios híbridos y de lista vinculada.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementación de una colección de pares de clave/valor

La colección genérica <xref:System.Collections.Generic.Dictionary%602> le permite tener acceso a los elementos de una colección con la clave de cada elemento. Cada adición al diccionario consta de un valor y de su clave asociada. Recuperar un valor usando su clave es rápido porque la clase `Dictionary` se implementa como una tabla hash.

En el ejemplo siguiente se crea una colección `Dictionary` y se recorre en iteración el diccionario usando una instrucción `foreach`.

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

Para usar un inicializador de colección para compilar la colección `Dictionary`, puede reemplazar los métodos `BuildDictionary` y `AddToDictionary` por el método siguiente.

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

En el ejemplo siguiente se usa el método <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> y la propiedad <xref:System.Collections.Generic.Dictionary%602.Item%2A> de `Dictionary` para encontrar rápidamente un elemento por clave. La propiedad `Item` le permite tener acceso a un elemento de la colección `elements` usando `elements[symbol]` en C#.

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

En el ejemplo siguiente se usa en su lugar el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para encontrar rápidamente un elemento por clave.

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

## <a name="using-linq-to-access-a-collection"></a>Uso de LINQ para tener acceso a una colección

LINQ (Language-Integrated Query) puede usar para tener acceso a las colecciones. Las consultas LINQ proporcionan capacidades de filtrado, ordenación y agrupación. Para obtener más información, vea [Introducción a LINQ en C#](linq/index.md).

El ejemplo siguiente ejecuta una consulta LINQ en una `List` genérica. La consulta LINQ devuelve otra colección que contiene los resultados.

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

## <a name="sorting-a-collection"></a>Ordenar una colección

En el ejemplo siguiente se muestra un procedimiento para ordenar una colección. El ejemplo ordena las instancias de la clase `Car` que se almacenan en un <xref:System.Collections.Generic.List%601>. La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.

Cada llamada al método <xref:System.IComparable%601.CompareTo%2A> realiza una comparación única que se usa para la ordenación. El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto. El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales. Esto permite definir en el código los criterios de mayor que, menor que e igual.

En el método `ListCars`, la instrucción `cars.Sort()` ordena la lista. Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que se llame automáticamente al método `CompareTo` para los objetos `Car` de `List`.

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

## <a name="defining-a-custom-collection"></a>Definición de una colección personalizada

Puede definir una colección implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>.

Aunque puede definir una colección personalizada, es mejor usar las colecciones incluidas en .NET Framework. Estas colecciones se describen en la sección [Tipos de colecciones](#BKMK_KindsOfCollections) de este tema.

En el siguiente ejemplo se define una clase de colección personalizada denominada `AllColors`. Esta clase implementa la interfaz <xref:System.Collections.IEnumerable> que requiere implementar el método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.

El método `GetEnumerator` devuelve una instancia de la clase `ColorEnumerator`. `ColorEnumerator` implementa la interfaz <xref:System.Collections.IEnumerator>, que requiere que la propiedad <xref:System.Collections.IEnumerator.Current%2A>, el método <xref:System.Collections.IEnumerator.MoveNext%2A> y el método <xref:System.Collections.IEnumerator.Reset%2A> estén implementados.

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

## <a name="iterators"></a>Iterators

Los *iteradores* se usan para efectuar una iteración personalizada en una colección. Un iterador puede ser un método o un descriptor de acceso `get`. Un iterador usa una instrucción [yield return](../../language-reference/keywords/yield.md) para devolver cada elemento de la colección a la vez.

Llame a un iterador mediante una instrucción [foreach](../../language-reference/keywords/foreach-in.md). Cada iteración del bucle `foreach` llama al iterador. Cuando se alcanza una instrucción `yield return` en el iterador, se devuelve una expresión y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.

Para obtener más información, vea [Iteradores (C#)](./iterators.md).

El siguiente ejemplo usa el método del iterador. El método del iterador tiene una instrucción `yield return` que se encuentra dentro de un bucle [for](../../language-reference/keywords/for.md). En el método `ListEvenNumbers`, cada iteración del cuerpo de la instrucción `foreach` crea una llamada al método iterador, que continúa con la siguiente instrucción `yield return`.

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

## <a name="see-also"></a>Vea también

- [Inicializadores de objeto y colección](../classes-and-structs/object-and-collection-initializers.md)
- [Conceptos de programación (C#)](./index.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (C#)](./linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ)](../../../standard/parallel-programming/introduction-to-plinq.md)
- [Colecciones y estructuras de datos](../../../standard/collections/index.md)
- [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md)
- [Comparaciones y ordenaciones en colecciones](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Cuándo utilizar colecciones genéricas](../../../standard/collections/when-to-use-generic-collections.md)
