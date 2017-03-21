---
title: Iteradores (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4ea1e21bd8cc392889c477e78338384ed05d4cbb
ms.lasthandoff: 03/13/2017

---
# <a name="iterators-visual-basic"></a>Iteradores (Visual Basic)
Un *iterador* puede utilizarse para recorrer colecciones como listas y matrices.  
  
 Un método iterador o `get` descriptor de acceso realiza una iteración personalizada en una colección. Utiliza un método iterador el [producen](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento de uno en uno. Cuando un `Yield` se alcanza la instrucción, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función de iterador.  
  
 Consumir un iterador del código de cliente mediante un [For Each... Siguiente](../../../visual-basic/language-reference/statements/for-each-next-statement.md) instrucción, o mediante una consulta LINQ.  
  
 En el ejemplo siguiente, la primera iteración de la `For Each` bucle hace que la ejecución continúe en la `SomeNumbers` método iterador hasta el primer `Yield` se alcanza la instrucción. Esta iteración devuelve un valor de 3 y se conserva la ubicación actual en el método iterador. En la siguiente iteración del bucle, la ejecución en el método iterador continúa desde donde lo dejó, deteniéndose de nuevo cuando llega un `Yield` instrucción. Esta iteración devuelve un valor de 5, y la ubicación actual en el método iterador nuevo se conserva. El bucle se completa cuando se alcanza el final del método iterador.  
  
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
  
 El tipo de valor devuelto de un método iterador o `get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
 Puede usar un `Exit Function` o `Return` instrucción para finalizar la iteración.  
  
 Una función de iterador de Visual Basic o `get` declaración de descriptor de acceso incluye una [iterador](../../../visual-basic/language-reference/modifiers/iterator.md) modificador.  
  
 Los iteradores se introdujeron en Visual Basic en Visual Studio 2012.  
  
 **En este tema**  
  
-   [Iterador simple](#BKMK_SimpleIterator)  
  
-   [Crear una clase de colección](#BKMK_CollectionClass)  
  
-   [Bloques try](#BKMK_TryBlocks)  
  
-   [Métodos anónimos](#BKMK_AnonymousMethods)  
  
-   [Uso de iteradores con una lista genérica](#BKMK_GenericList)  
  
-   [Información sobre la sintaxis](#BKMK_SyntaxInformation)  
  
-   [Implementación técnica](#BKMK_Technical)  
  
-   [Uso de iteradores](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  Para obtener todos los ejemplos en el tema excepto el ejemplo iterador Simple, incluyen [importaciones](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) instrucciones para el `System.Collections` y `System.Collections.Generic` los espacios de nombres.  
  
##  <a name="BKMK_SimpleIterator"></a>Iterador simple  
 En el siguiente ejemplo tiene un único `Yield` instrucción que se encuentra dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. En `Main`, cada iteración de la `For Each` cuerpo de instrucción crea una llamada a la función del iterador, que se dirige a la siguiente `Yield` instrucción.  
  
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
  
##  <a name="BKMK_CollectionClass"></a>Crear una clase de colección  
 En el ejemplo siguiente, la `DaysOfTheWeek` la clase implementa la <xref:System.Collections.IEnumerable>interfaz, que requiere un <xref:System.Collections.IEnumerable.GetEnumerator%2A>método.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable> El compilador llama implícitamente la `GetEnumerator` método, que devuelve un <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator>  
  
 El `GetEnumerator` método devuelve cada cadena uno a la vez mediante la `Yield` (instrucción) y un `Iterator` modificador está en la declaración de función.  
  
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
  
 En el ejemplo siguiente se crea un `Zoo` clase que contiene una colección de los animales.  
  
 El `For Each` instrucción que hace referencia a la instancia de clase (`theZoo`) llama implícitamente el `GetEnumerator` método. El `For Each` las instrucciones que hacen referencia a la `Birds` y `Mammals` propiedades utilizan el `AnimalsForType` denominado método iterador.  
  
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
  
##  <a name="BKMK_TryBlocks"></a>Bloques try  
 Visual Basic permite un `Yield` instrucción en el `Try` bloquear de un [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Un `Try` bloque con un `Yield` instrucción puede tener `Catch` bloquea y puede tener un `Finally` bloque.  
  
 En el ejemplo siguiente se incluye `Try`, `Catch`, y `Finally` bloques en una función de iterador. El `Finally` bloque en la función del iterador se ejecuta antes de la `For Each` iteración finaliza.  
  
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
  
 Un `Yield` instrucción no puede estar dentro de un `Catch` bloque o una `Finally` bloque.  
  
 Si el `For Each` cuerpo (en lugar del método iterador) produce una excepción, un `Catch` no se ejecuta el bloque de la función del iterador, pero un `Finally` se ejecuta el bloque de la función del iterador. Un `Catch` bloque dentro de una función de iterador captura solo las excepciones que se producen dentro de la función de iterador.  
  
##  <a name="BKMK_AnonymousMethods"></a>Métodos anónimos  
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
  
 En el siguiente ejemplo tiene un método no es de iterador que valida los argumentos. El método devuelve el resultado de un iterador anónimo que describe los elementos de la colección.  
  
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
  
 Si la validación está dentro de la función de iterador, no se puede realizar la validación hasta el inicio de la primera iteración de la `For Each` cuerpo.  
  
##  <a name="BKMK_GenericList"></a>Uso de iteradores con una lista genérica  
 En el ejemplo siguiente, la `Stack(Of T)` clase genérica implementa el <xref:System.Collections.Generic.IEnumerable%601>interfaz genérica.</xref:System.Collections.Generic.IEnumerable%601> El `Push` método asigna valores a una matriz de tipo `T`. El <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>método devuelve los valores de la matriz utilizando el `Yield` instrucción.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>  
  
 Además de la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>método, no genérica <xref:System.Collections.IEnumerable.GetEnumerator%2A>método debe implementarse también.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Esto es porque <xref:System.Collections.Generic.IEnumerable%601>se hereda de <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601> La implementación no genérica se pasa a la implementación genérica.  
  
 El ejemplo utiliza iteradores con nombre para admitir distintas formas de recorrer en iteración la misma colección de datos. Estos denominado iteradores son la `TopToBottom` y `BottomToTop` propiedades y la `TopN` (método).  
  
 El `BottomToTop` declaración de propiedad incluye la `Iterator` (palabra clave).  
  
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
  
##  <a name="BKMK_SyntaxInformation"></a>Información sobre la sintaxis  
 Un iterador se puede producir como un método o `get` descriptor de acceso. Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Debe existir una conversión implícita del tipo de expresión en el `Yield` instrucción para el tipo de valor devuelto del iterador.  
  
 En Visual Basic, no puede tener un método iterador ninguno `ByRef` parámetros.  
  
 En Visual Basic, "Rendimiento", no es una palabra reservada y tiene un significado especial solo cuando se utiliza en una `Iterator` método o `get` descriptor de acceso.  
  
##  <a name="BKMK_Technical"></a>Implementación técnica  
 Aunque escribir un iterador como un método, el compilador lo convierte en una clase anidada que es, en realidad, una máquina de Estados. Esta clase realiza un seguimiento de la posición del iterador como cuánto tiempo la `For Each...Next` continúa de bucle en el código de cliente.  
  
 Para ver lo que hace el compilador, puede utilizar la herramienta Ildasm.exe para ver el código de lenguaje intermedio de Microsoft que se genera para un método iterador.  
  
 Cuando se crea un iterador para una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), no es necesario implementar todo el <xref:System.Collections.IEnumerator>interfaz.</xref:System.Collections.IEnumerator> Cuando el compilador detecte el iterador, genera automáticamente el `Current`, `MoveNext`, y `Dispose` métodos de la <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>interfaz.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator>  
  
 En cada iteración sucesiva de la `For Each…Next` bucle (o la llamada directa a `IEnumerator.MoveNext`), el cuerpo de código del iterador siguiente se reanuda después de la anterior `Yield` instrucción. Después continúa con el siguiente `Yield` instrucción hasta que se alcanza el final del cuerpo del iterador, o hasta que un `Exit Function` o `Return` se encuentra la instrucción.  
  
 Los iteradores no admiten el <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>método.</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> Para volver a recorrer en iteración desde el principio, debe obtener un nuevo iterador.  
  
 Para obtener más información, consulte el [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
##  <a name="BKMK_UseOfIterators"></a>Uso de iteradores  
 Los iteradores permiten mantener la simplicidad de un `For Each` un bucle cuando necesite usar código complejo para rellenar una secuencia de la lista. Esto puede ser útil cuando desee hacer lo siguiente:  
  
-   Modificar la secuencia de la lista después de la primera `For Each` iteración de bucle.  
  
-   Evitar que se cargue totalmente una lista grande antes de la primera iteración de un `For Each` bucle. Un ejemplo es una búsqueda paginada para cargar un lote de filas de la tabla. Otro ejemplo es el <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>método, que implementa los iteradores en .NET Framework.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A>  
  
-   Encapsular la creación de la lista en el iterador. En el método iterador, puede crear la lista y, a continuación, se producen cada resultado en un bucle.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic></xref:System.Collections.Generic>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Yield (instrucción)](../../../visual-basic/language-reference/statements/yield-statement.md)   
 [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)
