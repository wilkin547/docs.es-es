---
title: 'Cómo: usar un grupo de subprocesos (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 90a0bb24-39f8-41f5-a217-b52a7d4fed0b
ms.openlocfilehash: a61defc2e40662d7fdadb40693e757fa559adb6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648156"
---
# <a name="how-to-use-a-thread-pool-visual-basic"></a><span data-ttu-id="fb346-102">Cómo: usar un grupo de subprocesos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb346-102">How to: Use a Thread Pool (Visual Basic)</span></span>
<span data-ttu-id="fb346-103">La *agrupación de subprocesos* es una forma de multithreading en la que se agregan tareas a una cola y se inician automáticamente cuando se crean subprocesos.</span><span class="sxs-lookup"><span data-stu-id="fb346-103">*Thread pooling* is a form of multithreading in which tasks are added to a queue and automatically started when threads are created.</span></span> <span data-ttu-id="fb346-104">Para obtener más información, consulte [agrupación de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="fb346-104">For more information, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md).</span></span>  
  
 <span data-ttu-id="fb346-105">En el ejemplo siguiente se usa el grupo de subprocesos de .NET Framework para calcular el resultado de `Fibonacci` para diez números entre 20 y 40.</span><span class="sxs-lookup"><span data-stu-id="fb346-105">The following example uses the .NET Framework thread pool to calculate the `Fibonacci` result for ten numbers between 20 and 40.</span></span> <span data-ttu-id="fb346-106">Cada resultado de `Fibonacci` se representa mediante la clase `Fibonacci`, que proporciona un método denominado `ThreadPoolCallback` que realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="fb346-106">Each `Fibonacci` result is represented by the `Fibonacci` class, which provides a method named `ThreadPoolCallback` that performs the calculation.</span></span> <span data-ttu-id="fb346-107">Se crea un objeto que representa cada valor de `Fibonacci` y el método `ThreadPoolCallback` se pasa a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, que asigna un subproceso disponible en el grupo para ejecutar el método.</span><span class="sxs-lookup"><span data-stu-id="fb346-107">An object that represents each `Fibonacci` value is created, and the `ThreadPoolCallback` method is passed to <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, which assigns an available thread in the pool to execute the method.</span></span>  
  
 <span data-ttu-id="fb346-108">Dado que a cada objeto `Fibonacci` se le asigna un valor semialeatorio para calcular y dado que cada subproceso compite para obtener tiempo de procesador, no se puede saber de antemano cuánto tardarán en calcularse los diez resultados.</span><span class="sxs-lookup"><span data-stu-id="fb346-108">Because each `Fibonacci` object is given a semi-random value to compute, and because each thread will be competing for processor time, you cannot know in advance how long it will take for all ten results to be calculated.</span></span> <span data-ttu-id="fb346-109">Por eso se pasa a cada objeto `Fibonacci` una instancia de la clase <xref:System.Threading.ManualResetEvent> durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="fb346-109">That is why each `Fibonacci` object is passed an instance of the <xref:System.Threading.ManualResetEvent> class during construction.</span></span> <span data-ttu-id="fb346-110">Cada objeto indica al objeto de evento proporcionado que su cálculo está completo, lo que permite que el subproceso principal bloquee la ejecución con <xref:System.Threading.WaitHandle.WaitAll%2A> hasta que los diez objetos `Fibonacci` hayan calculado un resultado.</span><span class="sxs-lookup"><span data-stu-id="fb346-110">Each object signals the provided event object when its calculation is complete, which allows the primary thread to block execution with <xref:System.Threading.WaitHandle.WaitAll%2A> until all ten `Fibonacci` objects have calculated a result.</span></span> <span data-ttu-id="fb346-111">El método `Main` muestra entonces cada resultado de `Fibonacci`.</span><span class="sxs-lookup"><span data-stu-id="fb346-111">The `Main` method then displays each `Fibonacci` result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb346-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb346-112">Example</span></span>  
  
```vb  
Imports System.Threading  
  
Module Module1  
  
    Public Class Fibonacci  
        Private _n As Integer  
        Private _fibOfN  
        Private _doneEvent As ManualResetEvent  
  
        Public ReadOnly Property N() As Integer  
            Get  
                Return _n  
            End Get  
        End Property  
  
        Public ReadOnly Property FibOfN() As Integer  
            Get  
                Return _fibOfN  
            End Get  
        End Property  
  
        Sub New(ByVal n As Integer, ByVal doneEvent As ManualResetEvent)  
            _n = n  
            _doneEvent = doneEvent  
        End Sub  
  
        ' Wrapper method for use with the thread pool.  
        Public Sub ThreadPoolCallBack(ByVal threadContext As Object)  
            Dim threadIndex As Integer = CType(threadContext, Integer)  
            Console.WriteLine("thread {0} started...", threadIndex)  
            _fibOfN = Calculate(_n)  
            Console.WriteLine("thread {0} result calculated...", threadIndex)  
            _doneEvent.Set()  
        End Sub  
  
        Public Function Calculate(ByVal n As Integer) As Integer  
            If n <= 1 Then  
                Return n  
            End If  
            Return Calculate(n - 1) + Calculate(n - 2)  
        End Function  
  
    End Class  
  
    <MTAThread()>   
    Sub Main()  
        Const FibonacciCalculations As Integer = 9 ' 0 to 9  
  
        ' One event is used for each Fibonacci object  
        Dim doneEvents(FibonacciCalculations) As ManualResetEvent  
        Dim fibArray(FibonacciCalculations) As Fibonacci  
        Dim r As New Random()  
  
        ' Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations)  
  
        For i As Integer = 0 To FibonacciCalculations  
            doneEvents(i) = New ManualResetEvent(False)  
            Dim f = New Fibonacci(r.Next(20, 40), doneEvents(i))  
            fibArray(i) = f  
            ThreadPool.QueueUserWorkItem(AddressOf f.ThreadPoolCallBack, i)  
        Next  
  
        ' Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents)  
        Console.WriteLine("All calculations are complete.")  
  
        ' Display the results.  
        For i As Integer = 0 To FibonacciCalculations  
            Dim f As Fibonacci = fibArray(i)  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN)  
        Next  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="fb346-113">El siguiente es un ejemplo de la salida.</span><span class="sxs-lookup"><span data-stu-id="fb346-113">Following is an example of the output.</span></span>  
  
```  
launching 10 tasks...  
thread 0 started...  
thread 1 started...  
thread 1 result calculated...  
thread 2 started...  
thread 2 result calculated...  
thread 3 started...  
thread 3 result calculated...  
thread 4 started...  
thread 0 result calculated...  
thread 5 started...  
thread 5 result calculated...  
thread 6 started...  
thread 4 result calculated...  
thread 7 started...  
thread 6 result calculated...  
thread 8 started...  
thread 8 result calculated...  
thread 9 started...  
thread 9 result calculated...  
thread 7 result calculated...  
All calculations are complete.  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(25) = 75025  
Fibonacci(22) = 17711  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(29) = 514229  
Fibonacci(38) = 39088169  
Fibonacci(21) = 10946  
Fibonacci(27) = 196418  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb346-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb346-114">See Also</span></span>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="fb346-115">Agrupación de subprocesos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb346-115">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="fb346-116">Subprocesamiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb346-116">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="fb346-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fb346-117">Security</span></span>](../../../../standard/security/index.md)
