---
description: 'Más información sobre: iteradores (Visual Basic)'
title: Iterators
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: 9d12bd436a976e3f84dbd063ca746fc7e3b17bfb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462157"
---
# <a name="iterators-visual-basic"></a>Iteradores (Visual Basic)

Un *iterador* puede usarse para recorrer colecciones como listas y matrices.

Un método iterador o un descriptor de acceso `get` realiza una iteración personalizada en una colección. Un método de iterador utiliza la instrucción [yield](../../language-reference/statements/yield-statement.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción `Yield`, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.

Un iterador se usa a partir del código de cliente mediante un [para cada... Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) o mediante una consulta LINQ.

En el ejemplo siguiente, la primera iteración del bucle `For Each` hace que continúe la ejecución del método de iterador `SomeNumbers` hasta que se alcance la primera instrucción `Yield`. Esta iteración devuelve un valor de 3, y la ubicación actual del método de iterador se conserva. En la siguiente iteración del bucle, la ejecución del método iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`. Esta iteración devuelve un valor de 5, y la ubicación actual del método de iterador se vuelve a conservar. El bucle se completa al alcanzar el final del método iterador.

```vb
Sub Main()
    For Each number As Integer In SomeNumbers()
        Console.Write(number & " ")
    Next
    ' Output: 3 5 8
    Console.ReadKey()
End Sub

Private Iterator Function SomeNumbers() As System.Collections.IEnumerable
    Yield 3
    Yield 5
    Yield 8
End Function
```

El tipo de valor devuelto de un método de iterador o descriptor de acceso `get` puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

Puede usar una `Exit Function` instrucción o `Return` para finalizar la iteración.

Una Visual Basic función de iterador o `get` declaración de descriptor de acceso incluye un modificador de [iterador](../../language-reference/modifiers/iterator.md) .

Los iteradores se introdujeron en Visual Basic en Visual Studio 2012.

**En este tema**

- [Iterador simple](#BKMK_SimpleIterator)

- [Creación de una clase de colección](#BKMK_CollectionClass)

- [Bloques try](#BKMK_TryBlocks)

- [Métodos anónimos](#BKMK_AnonymousMethods)

- [Uso de iteradores con una lista genérica](#BKMK_GenericList)

- [Información sobre la sintaxis](#BKMK_SyntaxInformation)

- [Implementación técnica](#BKMK_Technical)

- [Uso de iteradores](#BKMK_UseOfIterators)

> [!NOTE]
> En todos los ejemplos del tema excepto en el ejemplo de iterador simple, incluya instrucciones [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para los `System.Collections` `System.Collections.Generic` espacios de nombres y.

## <a name="simple-iterator"></a><a name="BKMK_SimpleIterator"></a> Iterador simple

El ejemplo siguiente tiene una única `Yield` instrucción que está dentro de un [... Siguiente](../../language-reference/statements/for-next-statement.md) bucle. En `Main`, cada iteración del cuerpo de la instrucción `For Each` crea una llamada a la función de iterador, que continúa a la instrucción `Yield` siguiente.

```vb
Sub Main()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    ' Output: 6 8 10 12 14 16 18
    Console.ReadKey()
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As System.Collections.Generic.IEnumerable(Of Integer)

    ' Yield even numbers in the range.
    For number As Integer = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="creating-a-collection-class"></a><a name="BKMK_CollectionClass"></a> Crear una clase de colección

En el ejemplo siguiente, la clase `DaysOfTheWeek` implementa la interfaz <xref:System.Collections.IEnumerable>, que requiere un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>. El compilador llama implícitamente al método `GetEnumerator`, que devuelve un <xref:System.Collections.IEnumerator>.

El `GetEnumerator` método devuelve cada cadena de una en una mediante la `Yield` instrucción y un `Iterator` modificador está en la declaración de función.

```vb
Sub Main()
    Dim days As New DaysOfTheWeek()
    For Each day As String In days
        Console.Write(day & " ")
    Next
    ' Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey()
End Sub

Private Class DaysOfTheWeek
    Implements IEnumerable

    Public days =
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        ' Yield each day of the week.
        For i As Integer = 0 To days.Length - 1
            Yield days(i)
        Next
    End Function
End Class
```

En el ejemplo siguiente se crea una clase `Zoo` que contiene una colección de animales.

La instrucción `For Each` que hace referencia a la instancia de clase (`theZoo`) llama implícitamente al método `GetEnumerator`. Las instrucciones `For Each` que hacen referencia a las propiedades `Birds` y `Mammals` usan el método iterador con el nombre `AnimalsForType`.

```vb
Sub Main()
    Dim theZoo As New Zoo()

    theZoo.AddMammal("Whale")
    theZoo.AddMammal("Rhinoceros")
    theZoo.AddBird("Penguin")
    theZoo.AddBird("Warbler")

    For Each name As String In theZoo
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros Penguin Warbler

    For Each name As String In theZoo.Birds
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Penguin Warbler

    For Each name As String In theZoo.Mammals
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros

    Console.ReadKey()
End Sub

Public Class Zoo
    Implements IEnumerable

    ' Private members.
    Private animals As New List(Of Animal)

    ' Public methods.
    Public Sub AddMammal(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})
    End Sub

    Public Sub AddBird(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})
    End Sub

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        For Each theAnimal As Animal In animals
            Yield theAnimal.Name
        Next
    End Function

    ' Public members.
    Public ReadOnly Property Mammals As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Mammal)
        End Get
    End Property

    Public ReadOnly Property Birds As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Bird)
        End Get
    End Property

    ' Private methods.
    Private Iterator Function AnimalsForType( _
    ByVal type As Animal.TypeEnum) As IEnumerable
        For Each theAnimal As Animal In animals
            If (theAnimal.Type = type) Then
                Yield theAnimal.Name
            End If
        Next
    End Function

    ' Private class.
    Private Class Animal
        Public Enum TypeEnum
            Bird
            Mammal
        End Enum

        Public Property Name As String
        Public Property Type As TypeEnum
    End Class
End Class
```

## <a name="try-blocks"></a><a name="BKMK_TryBlocks"></a> Bloques try

Visual Basic permite una `Yield` instrucción en el `Try` bloque de una instrucción [try... Detectar... Finally](../../language-reference/statements/try-catch-finally-statement.md). Un `Try` bloque que tiene una `Yield` instrucción puede tener `Catch` bloques y puede tener un `Finally` bloque.

En el ejemplo siguiente se incluyen los `Try` `Catch` bloques, y `Finally` en una función de iterador. El `Finally` bloque de la función de iterador se ejecuta antes de que `For Each` finalice la iteración.

```vb
Sub Main()
    For Each number As Integer In Test()
        Console.WriteLine(number)
    Next
    Console.WriteLine("For Each is done.")

    ' Output:
    '  3
    '  4
    '  Something happened. Yields are done.
    '  Finally is called.
    '  For Each is done.
    Console.ReadKey()
End Sub

Private Iterator Function Test() As IEnumerable(Of Integer)
    Try
        Yield 3
        Yield 4
        Throw New Exception("Something happened. Yields are done.")
        Yield 5
        Yield 6
    Catch ex As Exception
        Console.WriteLine(ex.Message)
    Finally
        Console.WriteLine("Finally is called.")
    End Try
End Function
```

Una `Yield` instrucción no puede estar dentro de un `Catch` bloque o un `Finally` bloque.

Si el `For Each` cuerpo (en lugar del método iterador) produce una excepción, `Catch` no se ejecuta un bloque de la función de iterador, pero `Finally` se ejecuta un bloque en la función de iterador. Un `Catch` bloque dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.

## <a name="anonymous-methods"></a><a name="BKMK_AnonymousMethods"></a> Métodos anónimos

En Visual Basic, una función anónima puede ser una función de iterador. Esto se ilustra en el siguiente ejemplo:

```vb
Dim iterateSequence = Iterator Function() _
                      As IEnumerable(Of Integer)
                          Yield 1
                          Yield 2
                      End Function

For Each number As Integer In iterateSequence()
    Console.Write(number & " ")
Next
' Output: 1 2
Console.ReadKey()
```

En el ejemplo siguiente hay un método que no es de iterador que valida los argumentos. El método devuelve el resultado de un iterador anónimo que describe los elementos de la colección.

```vb
Sub Main()
    For Each number As Integer In GetSequence(5, 10)
        Console.Write(number & " ")
    Next
    ' Output: 5 6 7 8 9 10
    Console.ReadKey()
End Sub

Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _
As IEnumerable
    ' Validate the arguments.
    If low < 1 Then
        Throw New ArgumentException("low is too low")
    End If
    If high > 140 Then
        Throw New ArgumentException("high is too high")
    End If

    ' Return an anonymous iterator function.
    Dim iterateSequence = Iterator Function() As IEnumerable
                              For index = low To high
                                  Yield index
                              Next
                          End Function
    Return iterateSequence()
End Function
```

Si la validación está en su lugar dentro de la función de iterador, no se puede realizar la validación hasta el inicio de la primera iteración del `For Each` cuerpo.

## <a name="using-iterators-with-a-generic-list"></a><a name="BKMK_GenericList"></a> Usar iteradores con una lista genérica

En el ejemplo siguiente, la clase genérica `Stack(Of T)` implementa la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>. El método `Push` asigna valores a una matriz de tipo `T`. El método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> devuelve los valores de la matriz con la instrucción `Yield`.

Además del método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> genérico, el método <xref:System.Collections.IEnumerable.GetEnumerator%2A> no genérico también debe implementarse. Esto es porque <xref:System.Collections.Generic.IEnumerable%601> se hereda de <xref:System.Collections.IEnumerable>. La implementación no genérica aplaza la implementación genérica.

El ejemplo usa iteradores con nombre para admitir distintas formas de recorrer en iteración la misma colección de datos. Estos iteradores con nombre son las propiedades `TopToBottom` y `BottomToTop`, y el método `TopN`.

La `BottomToTop` declaración de propiedad incluye la `Iterator` palabra clave.

```vb
Sub Main()
    Dim theStack As New Stack(Of Integer)

    ' Add items to the stack.
    For number As Integer = 0 To 9
        theStack.Push(number)
    Next

    ' Retrieve items from the stack.
    ' For Each is allowed because theStack implements
    ' IEnumerable(Of Integer).
    For Each number As Integer In theStack
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    ' For Each is allowed, because theStack.TopToBottom
    ' returns IEnumerable(Of Integer).
    For Each number As Integer In theStack.TopToBottom
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    For Each number As Integer In theStack.BottomToTop
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 0 1 2 3 4 5 6 7 8 9

    For Each number As Integer In theStack.TopN(7)
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3

    Console.ReadKey()
End Sub

Public Class Stack(Of T)
    Implements IEnumerable(Of T)

    Private values As T() = New T(99) {}
    Private top As Integer = 0

    Public Sub Push(ByVal t As T)
        values(top) = t
        top = top + 1
    End Sub

    Public Function Pop() As T
        top = top - 1
        Return values(top)
    End Function

    ' This function implements the GetEnumerator method. It allows
    ' an instance of the class to be used in a For Each statement.
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _
        Implements IEnumerable(Of T).GetEnumerator

        For index As Integer = top - 1 To 0 Step -1
            Yield values(index)
        Next
    End Function

    Public Iterator Function GetEnumerator1() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        Yield GetEnumerator()
    End Function

    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)
        Get
            Return Me
        End Get
    End Property

    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)
        Get
            For index As Integer = 0 To top - 1
                Yield values(index)
            Next
        End Get
    End Property

    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _
        As IEnumerable(Of T)

        ' Return less than itemsFromTop if necessary.
        Dim startIndex As Integer =
            If(itemsFromTop >= top, 0, top - itemsFromTop)

        For index As Integer = top - 1 To startIndex Step -1
            Yield values(index)
        Next
    End Function
End Class
```

## <a name="syntax-information"></a><a name="BKMK_SyntaxInformation"></a> Información de sintaxis

Un iterador se puede producir como un método o como un descriptor de acceso `get`. Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.

Debe existir una conversión implícita desde el tipo de expresión en la instrucción `Yield` al tipo de valor devuelto por el iterador.

En Visual Basic, un método de iterador no puede tener ningún `ByRef` parámetro.

En Visual Basic, "yield" no es una palabra reservada y tiene un significado especial solo cuando se usa en un `Iterator` método o un `get` descriptor de acceso.

## <a name="technical-implementation"></a><a name="BKMK_Technical"></a> Implementación técnica

Aunque un iterador se escribe como un método, el compilador lo traduce a una clase anidada que es, en realidad, una máquina de estados. Esta clase realiza el seguimiento de la posición del iterador mientras el bucle `For Each...Next` continúe en el código de cliente.

Para ver lo que hace el compilador, puede usar la herramienta Ildasm.exe para ver el código de lenguaje intermedio de Microsoft que se genera para un método iterador.

Cuando se crea un iterador para una [clase](../../language-reference/statements/class-statement.md) o [struct](../../language-reference/statements/structure-statement.md), no es necesario implementar toda la <xref:System.Collections.IEnumerator> interfaz. Cuando el compilador detecta el iterador, genera automáticamente los métodos `Current`, `MoveNext` y `Dispose` de la interfaz <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

En cada iteración sucesiva del bucle `For Each…Next` (o la llamada directa a `IEnumerator.MoveNext`), el cuerpo de código del iterador siguiente se reanuda después de la instrucción `Yield` anterior. Después, continúa con la siguiente `Yield` instrucción hasta que se alcanza el final del cuerpo del iterador o hasta que se encuentra una `Exit Function` `Return` instrucción o.

Los iteradores no admiten el <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> método. Para volver a recorrer en iteración desde el principio, se debe obtener un nuevo iterador.

Para obtener más información, vea la [especificación del lenguaje Visual Basic](../../reference/language-specification/index.md).

## <a name="use-of-iterators"></a><a name="BKMK_UseOfIterators"></a> Uso de iteradores

Los iteradores permiten mantener la simplicidad de un bucle `For Each` cuando se necesita usar código complejo para rellenar una secuencia de lista. Esto puede ser útil si quiere hacer lo siguiente:

- Modificar la secuencia de lista después de la primera iteración del bucle `For Each`.

- Evitar que se cargue totalmente una lista grande antes de la primera iteración de un bucle `For Each`. Un ejemplo es una búsqueda paginada para cargar un lote de filas de tabla. Otro ejemplo es el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que implementa iteradores en .NET Framework.

- Encapsular la creación de la lista en el iterador. En el método iterador, puede crear la lista y después devolver cada resultado en un bucle.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Instrucción For Each...Next](../../language-reference/statements/for-each-next-statement.md)
- [Instrucción Yield](../../language-reference/statements/yield-statement.md)
- [Iterator](../../language-reference/modifiers/iterator.md)
