---
title: "Cómo: Usar un grupo de subprocesos (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f90262cdfa6e4d6c8c37c553e999d51fee736d6a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-a-thread-pool-c"></a>Cómo: Usar un grupo de subprocesos (C#)
La *agrupación de subprocesos* es una forma de multithreading en la que se agregan tareas a una cola y se inician automáticamente cuando se crean subprocesos. Para obtener más información, vea [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) (Agrupación de subprocesos [C#]).  
  
 En el ejemplo siguiente se usa el grupo de subprocesos de .NET Framework para calcular el resultado de `Fibonacci` para diez números entre 20 y 40. Cada resultado de `Fibonacci` se representa mediante la clase `Fibonacci`, que proporciona un método denominado `ThreadPoolCallback` que realiza el cálculo. Se crea un objeto que representa cada valor de `Fibonacci` y el método `ThreadPoolCallback` se pasa a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, que asigna un subproceso disponible en el grupo para ejecutar el método.  
  
 Dado que a cada objeto `Fibonacci` se le asigna un valor semialeatorio para calcular y dado que cada subproceso compite para obtener tiempo de procesador, no se puede saber de antemano cuánto tardarán en calcularse los diez resultados. Por eso se pasa a cada objeto `Fibonacci` una instancia de la clase <xref:System.Threading.ManualResetEvent> durante la construcción. Cada objeto indica al objeto de evento proporcionado que su cálculo está completo, lo que permite que el subproceso principal bloquee la ejecución con <xref:System.Threading.WaitHandle.WaitAll%2A> hasta que los diez objetos `Fibonacci` hayan calculado un resultado. El método `Main` muestra entonces cada resultado de `Fibonacci`.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
using System;  
using System.Threading;  
  
public class Fibonacci  
{  
    private int _n;  
    private int _fibOfN;  
    private ManualResetEvent _doneEvent;  
  
    public int N { get { return _n; } }  
    public int FibOfN { get { return _fibOfN; } }  
  
    // Constructor.  
    public Fibonacci(int n, ManualResetEvent doneEvent)  
    {  
        _n = n;  
        _doneEvent = doneEvent;  
    }  
  
    // Wrapper method for use with thread pool.  
    public void ThreadPoolCallback(Object threadContext)  
    {  
        int threadIndex = (int)threadContext;  
        Console.WriteLine("thread {0} started...", threadIndex);  
        _fibOfN = Calculate(_n);  
        Console.WriteLine("thread {0} result calculated...", threadIndex);  
        _doneEvent.Set();  
    }  
  
    // Recursive method that calculates the Nth Fibonacci number.  
    public int Calculate(int n)  
    {  
        if (n <= 1)  
        {  
            return n;  
        }  
  
        return Calculate(n - 1) + Calculate(n - 2);  
    }  
}  
  
public class ThreadPoolExample  
{  
    static void Main()  
    {  
        const int FibonacciCalculations = 10;  
  
        // One event is used for each Fibonacci object.  
        ManualResetEvent[] doneEvents = new ManualResetEvent[FibonacciCalculations];  
        Fibonacci[] fibArray = new Fibonacci[FibonacciCalculations];  
        Random r = new Random();  
  
        // Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations);  
        for (int i = 0; i < FibonacciCalculations; i++)  
        {  
            doneEvents[i] = new ManualResetEvent(false);  
            Fibonacci f = new Fibonacci(r.Next(20, 40), doneEvents[i]);  
            fibArray[i] = f;  
            ThreadPool.QueueUserWorkItem(f.ThreadPoolCallback, i);  
        }  
  
        // Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents);  
        Console.WriteLine("All calculations are complete.");  
  
        // Display the results.  
        for (int i= 0; i<FibonacciCalculations; i++)  
        {  
            Fibonacci f = fibArray[i];  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN);  
        }  
    }  
}  
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
 [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  (Agrupación de subprocesos [C#])  
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  (Subprocesos [C#])  
 @System.Threading.Monitor   
 [Seguridad](../../../../standard/security/index.md)

