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
# <a name="iterators-visual-basic"></a><span data-ttu-id="b5965-103">Iteradores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5965-103">Iterators (Visual Basic)</span></span>

<span data-ttu-id="b5965-104">Un *iterador* puede usarse para recorrer colecciones como listas y matrices.</span><span class="sxs-lookup"><span data-stu-id="b5965-104">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="b5965-105">Un método iterador o un descriptor de acceso `get` realiza una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="b5965-105">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="b5965-106">Un método de iterador utiliza la instrucción [yield](../../language-reference/statements/yield-statement.md) para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="b5965-106">An iterator method uses the [Yield](../../language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="b5965-107">Cuando se alcanza una instrucción `Yield`, se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="b5965-107">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="b5965-108">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-108">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="b5965-109">Un iterador se usa a partir del código de cliente mediante un [para cada... Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md) o mediante una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="b5965-109">You consume an iterator from client code by using a [For Each…Next](../../language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>

<span data-ttu-id="b5965-110">En el ejemplo siguiente, la primera iteración del bucle `For Each` hace que continúe la ejecución del método de iterador `SomeNumbers` hasta que se alcance la primera instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b5965-110">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="b5965-111">Esta iteración devuelve un valor de 3, y la ubicación actual del método de iterador se conserva.</span><span class="sxs-lookup"><span data-stu-id="b5965-111">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="b5965-112">En la siguiente iteración del bucle, la ejecución del método iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b5965-112">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="b5965-113">Esta iteración devuelve un valor de 5, y la ubicación actual del método de iterador se vuelve a conservar.</span><span class="sxs-lookup"><span data-stu-id="b5965-113">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="b5965-114">El bucle se completa al alcanzar el final del método iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-114">The loop completes when the end of the iterator method is reached.</span></span>

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

<span data-ttu-id="b5965-115">El tipo de valor devuelto de un método de iterador o descriptor de acceso `get` puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="b5965-115">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="b5965-116">Puede usar una `Exit Function` instrucción o `Return` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="b5965-116">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>

<span data-ttu-id="b5965-117">Una Visual Basic función de iterador o `get` declaración de descriptor de acceso incluye un modificador de [iterador](../../language-reference/modifiers/iterator.md) .</span><span class="sxs-lookup"><span data-stu-id="b5965-117">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../language-reference/modifiers/iterator.md) modifier.</span></span>

<span data-ttu-id="b5965-118">Los iteradores se introdujeron en Visual Basic en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b5965-118">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>

<span data-ttu-id="b5965-119">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b5965-119">**In this topic**</span></span>

- [<span data-ttu-id="b5965-120">Iterador simple</span><span class="sxs-lookup"><span data-stu-id="b5965-120">Simple Iterator</span></span>](#BKMK_SimpleIterator)

- [<span data-ttu-id="b5965-121">Creación de una clase de colección</span><span class="sxs-lookup"><span data-stu-id="b5965-121">Creating a Collection Class</span></span>](#BKMK_CollectionClass)

- [<span data-ttu-id="b5965-122">Bloques try</span><span class="sxs-lookup"><span data-stu-id="b5965-122">Try Blocks</span></span>](#BKMK_TryBlocks)

- [<span data-ttu-id="b5965-123">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="b5965-123">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)

- [<span data-ttu-id="b5965-124">Uso de iteradores con una lista genérica</span><span class="sxs-lookup"><span data-stu-id="b5965-124">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)

- [<span data-ttu-id="b5965-125">Información sobre la sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5965-125">Syntax Information</span></span>](#BKMK_SyntaxInformation)

- [<span data-ttu-id="b5965-126">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="b5965-126">Technical Implementation</span></span>](#BKMK_Technical)

- [<span data-ttu-id="b5965-127">Uso de iteradores</span><span class="sxs-lookup"><span data-stu-id="b5965-127">Use of Iterators</span></span>](#BKMK_UseOfIterators)

> [!NOTE]
> <span data-ttu-id="b5965-128">En todos los ejemplos del tema excepto en el ejemplo de iterador simple, incluya instrucciones [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para los `System.Collections` `System.Collections.Generic` espacios de nombres y.</span><span class="sxs-lookup"><span data-stu-id="b5965-128">For all examples in the topic except the Simple Iterator example, include [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="simple-iterator"></a><a name="BKMK_SimpleIterator"></a> <span data-ttu-id="b5965-129">Iterador simple</span><span class="sxs-lookup"><span data-stu-id="b5965-129">Simple Iterator</span></span>

<span data-ttu-id="b5965-130">El ejemplo siguiente tiene una única `Yield` instrucción que está dentro de un [... Siguiente](../../language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="b5965-130">The following example has a single `Yield` statement that is inside a [For…Next](../../language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="b5965-131">En `Main`, cada iteración del cuerpo de la instrucción `For Each` crea una llamada a la función de iterador, que continúa a la instrucción `Yield` siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5965-131">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>

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

## <a name="creating-a-collection-class"></a><a name="BKMK_CollectionClass"></a> <span data-ttu-id="b5965-132">Crear una clase de colección</span><span class="sxs-lookup"><span data-stu-id="b5965-132">Creating a Collection Class</span></span>

<span data-ttu-id="b5965-133">En el ejemplo siguiente, la clase `DaysOfTheWeek` implementa la interfaz <xref:System.Collections.IEnumerable>, que requiere un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5965-133">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="b5965-134">El compilador llama implícitamente al método `GetEnumerator`, que devuelve un <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="b5965-134">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="b5965-135">El `GetEnumerator` método devuelve cada cadena de una en una mediante la `Yield` instrucción y un `Iterator` modificador está en la declaración de función.</span><span class="sxs-lookup"><span data-stu-id="b5965-135">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>

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

<span data-ttu-id="b5965-136">En el ejemplo siguiente se crea una clase `Zoo` que contiene una colección de animales.</span><span class="sxs-lookup"><span data-stu-id="b5965-136">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="b5965-137">La instrucción `For Each` que hace referencia a la instancia de clase (`theZoo`) llama implícitamente al método `GetEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="b5965-137">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="b5965-138">Las instrucciones `For Each` que hacen referencia a las propiedades `Birds` y `Mammals` usan el método iterador con el nombre `AnimalsForType`.</span><span class="sxs-lookup"><span data-stu-id="b5965-138">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

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

## <a name="try-blocks"></a><a name="BKMK_TryBlocks"></a> <span data-ttu-id="b5965-139">Bloques try</span><span class="sxs-lookup"><span data-stu-id="b5965-139">Try Blocks</span></span>

<span data-ttu-id="b5965-140">Visual Basic permite una `Yield` instrucción en el `Try` bloque de una instrucción [try... Detectar... Finally](../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5965-140">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="b5965-141">Un `Try` bloque que tiene una `Yield` instrucción puede tener `Catch` bloques y puede tener un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="b5965-141">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>

<span data-ttu-id="b5965-142">En el ejemplo siguiente se incluyen los `Try` `Catch` bloques, y `Finally` en una función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-142">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="b5965-143">El `Finally` bloque de la función de iterador se ejecuta antes de que `For Each` finalice la iteración.</span><span class="sxs-lookup"><span data-stu-id="b5965-143">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>

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

<span data-ttu-id="b5965-144">Una `Yield` instrucción no puede estar dentro de un `Catch` bloque o un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="b5965-144">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>

<span data-ttu-id="b5965-145">Si el `For Each` cuerpo (en lugar del método iterador) produce una excepción, `Catch` no se ejecuta un bloque de la función de iterador, pero `Finally` se ejecuta un bloque en la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-145">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="b5965-146">Un `Catch` bloque dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-146">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>

## <a name="anonymous-methods"></a><a name="BKMK_AnonymousMethods"></a> <span data-ttu-id="b5965-147">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="b5965-147">Anonymous Methods</span></span>

<span data-ttu-id="b5965-148">En Visual Basic, una función anónima puede ser una función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-148">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="b5965-149">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5965-149">The following example illustrates this.</span></span>

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

<span data-ttu-id="b5965-150">En el ejemplo siguiente hay un método que no es de iterador que valida los argumentos.</span><span class="sxs-lookup"><span data-stu-id="b5965-150">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="b5965-151">El método devuelve el resultado de un iterador anónimo que describe los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="b5965-151">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>

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

<span data-ttu-id="b5965-152">Si la validación está en su lugar dentro de la función de iterador, no se puede realizar la validación hasta el inicio de la primera iteración del `For Each` cuerpo.</span><span class="sxs-lookup"><span data-stu-id="b5965-152">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>

## <a name="using-iterators-with-a-generic-list"></a><a name="BKMK_GenericList"></a> <span data-ttu-id="b5965-153">Usar iteradores con una lista genérica</span><span class="sxs-lookup"><span data-stu-id="b5965-153">Using Iterators with a Generic List</span></span>

<span data-ttu-id="b5965-154">En el ejemplo siguiente, la clase genérica `Stack(Of T)` implementa la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b5965-154">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="b5965-155">El método `Push` asigna valores a una matriz de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="b5965-155">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="b5965-156">El método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> devuelve los valores de la matriz con la instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b5965-156">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>

<span data-ttu-id="b5965-157">Además del método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> genérico, el método <xref:System.Collections.IEnumerable.GetEnumerator%2A> no genérico también debe implementarse.</span><span class="sxs-lookup"><span data-stu-id="b5965-157">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="b5965-158">Esto es porque <xref:System.Collections.Generic.IEnumerable%601> se hereda de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="b5965-158">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="b5965-159">La implementación no genérica aplaza la implementación genérica.</span><span class="sxs-lookup"><span data-stu-id="b5965-159">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="b5965-160">El ejemplo usa iteradores con nombre para admitir distintas formas de recorrer en iteración la misma colección de datos.</span><span class="sxs-lookup"><span data-stu-id="b5965-160">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="b5965-161">Estos iteradores con nombre son las propiedades `TopToBottom` y `BottomToTop`, y el método `TopN`.</span><span class="sxs-lookup"><span data-stu-id="b5965-161">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="b5965-162">La `BottomToTop` declaración de propiedad incluye la `Iterator` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b5965-162">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>

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

## <a name="syntax-information"></a><a name="BKMK_SyntaxInformation"></a> <span data-ttu-id="b5965-163">Información de sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5965-163">Syntax Information</span></span>

<span data-ttu-id="b5965-164">Un iterador se puede producir como un método o como un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="b5965-164">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="b5965-165">Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="b5965-165">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>

<span data-ttu-id="b5965-166">Debe existir una conversión implícita desde el tipo de expresión en la instrucción `Yield` al tipo de valor devuelto por el iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-166">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>

<span data-ttu-id="b5965-167">En Visual Basic, un método de iterador no puede tener ningún `ByRef` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5965-167">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>

<span data-ttu-id="b5965-168">En Visual Basic, "yield" no es una palabra reservada y tiene un significado especial solo cuando se usa en un `Iterator` método o un `get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="b5965-168">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>

## <a name="technical-implementation"></a><a name="BKMK_Technical"></a> <span data-ttu-id="b5965-169">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="b5965-169">Technical Implementation</span></span>

<span data-ttu-id="b5965-170">Aunque un iterador se escribe como un método, el compilador lo traduce a una clase anidada que es, en realidad, una máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="b5965-170">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="b5965-171">Esta clase realiza el seguimiento de la posición del iterador mientras el bucle `For Each...Next` continúe en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="b5965-171">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>

<span data-ttu-id="b5965-172">Para ver lo que hace el compilador, puede usar la herramienta Ildasm.exe para ver el código de lenguaje intermedio de Microsoft que se genera para un método iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-172">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>

<span data-ttu-id="b5965-173">Cuando se crea un iterador para una [clase](../../language-reference/statements/class-statement.md) o [struct](../../language-reference/statements/structure-statement.md), no es necesario implementar toda la <xref:System.Collections.IEnumerator> interfaz.</span><span class="sxs-lookup"><span data-stu-id="b5965-173">When you create an iterator for a [class](../../language-reference/statements/class-statement.md) or [struct](../../language-reference/statements/structure-statement.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="b5965-174">Cuando el compilador detecta el iterador, genera automáticamente los métodos `Current`, `MoveNext` y `Dispose` de la interfaz <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="b5965-174">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="b5965-175">En cada iteración sucesiva del bucle `For Each…Next` (o la llamada directa a `IEnumerator.MoveNext`), el cuerpo de código del iterador siguiente se reanuda después de la instrucción `Yield` anterior.</span><span class="sxs-lookup"><span data-stu-id="b5965-175">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="b5965-176">Después, continúa con la siguiente `Yield` instrucción hasta que se alcanza el final del cuerpo del iterador o hasta que se encuentra una `Exit Function` `Return` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="b5965-176">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>

<span data-ttu-id="b5965-177">Los iteradores no admiten el <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="b5965-177">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b5965-178">Para volver a recorrer en iteración desde el principio, se debe obtener un nuevo iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-178">To re-iterate from the start, you must obtain a new iterator.</span></span>

<span data-ttu-id="b5965-179">Para obtener más información, vea la [especificación del lenguaje Visual Basic](../../reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b5965-179">For additional information, see the [Visual Basic Language Specification](../../reference/language-specification/index.md).</span></span>

## <a name="use-of-iterators"></a><a name="BKMK_UseOfIterators"></a> <span data-ttu-id="b5965-180">Uso de iteradores</span><span class="sxs-lookup"><span data-stu-id="b5965-180">Use of Iterators</span></span>

<span data-ttu-id="b5965-181">Los iteradores permiten mantener la simplicidad de un bucle `For Each` cuando se necesita usar código complejo para rellenar una secuencia de lista.</span><span class="sxs-lookup"><span data-stu-id="b5965-181">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="b5965-182">Esto puede ser útil si quiere hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5965-182">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="b5965-183">Modificar la secuencia de lista después de la primera iteración del bucle `For Each`.</span><span class="sxs-lookup"><span data-stu-id="b5965-183">Modify the list sequence after the first `For Each` loop iteration.</span></span>

- <span data-ttu-id="b5965-184">Evitar que se cargue totalmente una lista grande antes de la primera iteración de un bucle `For Each`.</span><span class="sxs-lookup"><span data-stu-id="b5965-184">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="b5965-185">Un ejemplo es una búsqueda paginada para cargar un lote de filas de tabla.</span><span class="sxs-lookup"><span data-stu-id="b5965-185">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="b5965-186">Otro ejemplo es el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que implementa iteradores en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5965-186">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>

- <span data-ttu-id="b5965-187">Encapsular la creación de la lista en el iterador.</span><span class="sxs-lookup"><span data-stu-id="b5965-187">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="b5965-188">En el método iterador, puede crear la lista y después devolver cada resultado en un bucle.</span><span class="sxs-lookup"><span data-stu-id="b5965-188">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5965-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5965-189">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="b5965-190">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="b5965-190">For Each...Next Statement</span></span>](../../language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="b5965-191">Instrucción Yield</span><span class="sxs-lookup"><span data-stu-id="b5965-191">Yield Statement</span></span>](../../language-reference/statements/yield-statement.md)
- [<span data-ttu-id="b5965-192">Iterator</span><span class="sxs-lookup"><span data-stu-id="b5965-192">Iterator</span></span>](../../language-reference/modifiers/iterator.md)
