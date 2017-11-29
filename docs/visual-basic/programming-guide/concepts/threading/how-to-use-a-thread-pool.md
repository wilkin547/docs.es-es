---
title: "Cómo: usar un grupo de subprocesos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90a0bb24-39f8-41f5-a217-b52a7d4fed0b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42a4120900203eb7eb5ad8463fba4491636882b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-thread-pool-visual-basic"></a>Cómo: usar un grupo de subprocesos (Visual Basic)
La *agrupación de subprocesos* es una forma de multithreading en la que se agregan tareas a una cola y se inician automáticamente cuando se crean subprocesos. Para obtener más información, consulte [agrupación de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md).  
  
 En el ejemplo siguiente se usa el grupo de subprocesos de .NET Framework para calcular el resultado de `Fibonacci` para diez números entre 20 y 40. Cada resultado de `Fibonacci` se representa mediante la clase `Fibonacci`, que proporciona un método denominado `ThreadPoolCallback` que realiza el cálculo. Se crea un objeto que representa cada valor de `Fibonacci` y el método `ThreadPoolCallback` se pasa a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, que asigna un subproceso disponible en el grupo para ejecutar el método.  
  
 Dado que a cada objeto `Fibonacci` se le asigna un valor semialeatorio para calcular y dado que cada subproceso compite para obtener tiempo de procesador, no se puede saber de antemano cuánto tardarán en calcularse los diez resultados. Por eso se pasa a cada objeto `Fibonacci` una instancia de la clase <xref:System.Threading.ManualResetEvent> durante la construcción. Cada objeto indica al objeto de evento proporcionado que su cálculo está completo, lo que permite que el subproceso principal bloquee la ejecución con <xref:System.Threading.WaitHandle.WaitAll%2A> hasta que los diez objetos `Fibonacci` hayan calculado un resultado. El método `Main` muestra entonces cada resultado de `Fibonacci`.  
  
## <a name="example"></a>Ejemplo  
  
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
  
 El siguiente es un ejemplo de la salida.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [Agrupación de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Seguridad](../../../../standard/security/index.md)
