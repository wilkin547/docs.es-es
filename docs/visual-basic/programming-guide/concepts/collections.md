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
# <a name="collections-visual-basic"></a>Colecciones (Visual Basic)

Para muchas aplicaciones, puede que desee crear y administrar grupos de objetos relacionados. Existen dos formas de agrupar objetos: mediante la creación de matrices de objetos y con la creación de colecciones de objetos.

Las matrices son muy útiles para crear y trabajar con un número fijo de objetos fuertemente tipados. Para obtener información sobre las matrices, vea [Matrices](../language-features/arrays/index.md).

Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. A diferencia de las matrices, el grupo de objetos con el que trabaja puede aumentar y reducirse de manera dinámica a medida que cambian las necesidades de la aplicación. Para algunas colecciones, puede asignar una clave a cualquier objeto que incluya en la colección para, de este modo, recuperar rápidamente el objeto con la clave.

Una colección es una clase, por lo que debe declarar una instancia de la clase para poder agregar elementos a dicha colección.

Si la colección contiene elementos de un solo tipo de datos, puede usar una de las clases del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType>. Una colección genérica cumple la seguridad de tipos para que ningún otro tipo de datos se pueda agregar a ella. Cuando recupera un elemento de una colección genérica, no tiene que determinar su tipo de datos ni convertirlo.

> [!NOTE]
> Para ver los ejemplos de este tema, incluya instrucciones [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para los `System.Collections.Generic` espacios de `System.Linq` nombres y.

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Uso de una colección Simple

Los ejemplos de esta sección usan la clase genérica <xref:System.Collections.Generic.List%601>, que le permite trabajar con una lista de objetos fuertemente tipados.

En el ejemplo siguiente se crea una lista de cadenas y, a continuación, se recorre en iteración las cadenas mediante una... [ Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) .

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

Si el contenido de una colección se conoce de antemano, puede usar un *inicializador de colección* para inicializar la colección. Para obtener más información, vea [Inicializadores de colección](../language-features/collection-initializers/index.md).

El ejemplo siguiente es el mismo que el ejemplo anterior, excepto que se usa un inicializador de colección para agregar elementos a la colección.

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

Puede usar una [... Instrucción Next](../../language-reference/statements/for-next-statement.md) en lugar de una `For Each` instrucción para recorrer en iteración una colección. Esto se consigue con el acceso a los elementos de la colección mediante la posición de índice. El índice de los elementos comienza en 0 y termina en el número de elementos menos 1.

El ejemplo siguiente recorre en iteración los elementos de una colección mediante `For…Next` en lugar de `For Each`.

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

El ejemplo siguiente quita un elemento de la colección especificando el objeto que se quitará.

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

El ejemplo siguiente quita elementos de una lista genérica. En lugar de una `For Each` instrucción, una instrucción [for... ](../../language-reference/statements/for-next-statement.md) Se usa la siguiente instrucción que recorre en iteración en orden descendente. Esto es porque el método <xref:System.Collections.Generic.List%601.RemoveAt%2A> hace que los elementos después de un elemento quitado tengan un valor de índice inferior.

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

Para el tipo de elementos de <xref:System.Collections.Generic.List%601>, también puede definir su propia clase. En el ejemplo siguiente, la clase `Galaxy` que usa <xref:System.Collections.Generic.List%601> se define en el código.

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

## <a name="kinds-of-collections"></a>Tipos de colecciones

.NET Framework proporciona muchas colecciones comunes. Cada tipo de colección está diseñado para un fin específico.

En esta sección se describen algunas de las clases de colecciones comunes:

- Clases <xref:System.Collections.Generic>

- Clases <xref:System.Collections.Concurrent>

- Clases <xref:System.Collections>

- Clase `Collection` de Visual Basic

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

Para obtener más información, vea [Tipos de colección utilizados normalmente](../../../standard/collections/commonly-used-collection-types.md), [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md) y <xref:System.Collections.Generic?displayProperty=nameWithType>.

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

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a>Clase de colección de Visual Basic

Puede usar la clase de Visual Basic <xref:Microsoft.VisualBasic.Collection> para tener acceso a un elemento de colección mediante un índice numérico o una clave `String`. Puede agregar elementos a un objeto de colección especificando o sin especificar clave. Si agrega un elemento sin clave, debe usar su índice numérico para tener acceso a dicho elemento.

La clase de Visual Basic `Collection` almacena todos sus elementos como de tipo `Object`, por lo que puede agregar un elemento de cualquier tipo de datos. No hay ningún método de protección contra los tipos de datos inadecuados agregados.

Cuando se usa la clase de Visual Basic `Collection`, el primer elemento de una colección tiene un índice de 1. Esto difiere de las clases de colección de .NET Framework, para las cuales el índice inicial es 0.

Siempre que sea posible, debe usar las colecciones genéricas del espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> o del espacio de nombres <xref:System.Collections.Concurrent> en lugar de la clase de Visual Basic `Collection`.

Para obtener más información, vea <xref:Microsoft.VisualBasic.Collection>.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementación de una colección de pares de clave/valor

La colección genérica <xref:System.Collections.Generic.Dictionary%602> le permite tener acceso a los elementos de una colección con la clave de cada elemento. Cada adición al diccionario consta de un valor y de su clave asociada. Recuperar un valor usando su clave es rápido porque la clase `Dictionary` se implementa como una tabla hash.

En el ejemplo siguiente se crea una colección `Dictionary` y se recorre en iteración el diccionario usando una instrucción `For Each`.

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

Para usar un inicializador de colección para compilar la colección `Dictionary`, puede reemplazar los métodos `BuildDictionary` y `AddToDictionary` por el método siguiente.

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

En el ejemplo siguiente se usa el método <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> y la propiedad <xref:System.Collections.Generic.Dictionary%602.Item%2A> de `Dictionary` para encontrar rápidamente un elemento por clave. La `Item` propiedad le permite tener acceso a un elemento de la `elements` colección utilizando el `elements(symbol)` código de Visual Basic.

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

En el ejemplo siguiente se usa en su lugar el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para encontrar rápidamente un elemento por clave.

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

## <a name="using-linq-to-access-a-collection"></a>Uso de LINQ para tener acceso a una colección

LINQ (Language-Integrated Query) puede usar para tener acceso a las colecciones. Las consultas LINQ proporcionan capacidades de filtrado, ordenación y agrupación. Para obtener más información, vea [Introducción con LINQ en Visual Basic](linq/getting-started-with-linq.md).

El ejemplo siguiente ejecuta una consulta LINQ en una `List` genérica. La consulta LINQ devuelve otra colección que contiene los resultados.

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

## <a name="sorting-a-collection"></a>Ordenar una colección

En el ejemplo siguiente se muestra un procedimiento para ordenar una colección. El ejemplo ordena las instancias de la clase `Car` que se almacenan en un <xref:System.Collections.Generic.List%601>. La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.

Cada llamada al método <xref:System.IComparable%601.CompareTo%2A> realiza una comparación única que se usa para la ordenación. El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto. El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales. Esto permite definir en el código los criterios de mayor que, menor que e igual.

En el método `ListCars`, la instrucción `cars.Sort()` ordena la lista. Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que se llame automáticamente al método `CompareTo` para los objetos `Car` de `List`.

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

## <a name="defining-a-custom-collection"></a>Definición de una colección personalizada

Puede definir una colección implementando la interfaz <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>. Para obtener más información, vea [enumerar una colección](/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).

Aunque puede definir una colección personalizada, es mejor usar las colecciones incluidas en .NET Framework. Estas colecciones se describen en la sección [Tipos de colecciones](#kinds-of-collections) de este tema.

En el siguiente ejemplo se define una clase de colección personalizada denominada `AllColors`. Esta clase implementa la interfaz <xref:System.Collections.IEnumerable> que requiere implementar el método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.

El método `GetEnumerator` devuelve una instancia de la clase `ColorEnumerator`. `ColorEnumerator` implementa la interfaz <xref:System.Collections.IEnumerator>, que requiere que la propiedad <xref:System.Collections.IEnumerator.Current%2A>, el método <xref:System.Collections.IEnumerator.MoveNext%2A> y el método <xref:System.Collections.IEnumerator.Reset%2A> estén implementados.

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

## <a name="iterators"></a>Iterators

Los *iteradores* se usan para efectuar una iteración personalizada en una colección. Un iterador puede ser un método o un descriptor de acceso `get`. Un iterador usa una instrucción [yield](../../language-reference/statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno.

Se llama a un iterador mediante un método [for each... Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) . Cada iteración del bucle `For Each` llama al iterador. Cuando se alcanza una instrucción `Yield` en el iterador, se devuelve una expresión y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.

Para obtener más información, vea [iteradores (Visual Basic)](iterators.md).

El siguiente ejemplo usa el método del iterador. El método iterador tiene una `Yield` instrucción que está dentro [de un... Siguiente](../../language-reference/statements/for-next-statement.md) bucle. En el método `ListEvenNumbers`, cada iteración del cuerpo de la instrucción `For Each` crea una llamada al método iterador, que continúa con la siguiente instrucción `Yield`.

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

## <a name="see-also"></a>Vea también

- [Inicializadores de colección](../language-features/collection-initializers/index.md)
- [Conceptos de programación (Visual Basic)](index.md)
- [Option Strict (instrucción)](../../language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (Visual Basic)](linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ)](../../../standard/parallel-programming/introduction-to-plinq.md)
- [Colecciones y estructuras de datos](../../../standard/collections/index.md)
- [Seleccionar una clase de colección](../../../standard/collections/selecting-a-collection-class.md)
- [Comparaciones y ordenaciones en colecciones](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Cuándo utilizar colecciones genéricas](../../../standard/collections/when-to-use-generic-collections.md)
