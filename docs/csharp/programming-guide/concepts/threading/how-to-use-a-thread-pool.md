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
# <a name="how-to-use-a-thread-pool-c"></a><span data-ttu-id="78629-102">Cómo: Usar un grupo de subprocesos (C#)</span><span class="sxs-lookup"><span data-stu-id="78629-102">How to: Use a Thread Pool (C#)</span></span>
<span data-ttu-id="78629-103">La *agrupación de subprocesos* es una forma de multithreading en la que se agregan tareas a una cola y se inician automáticamente cuando se crean subprocesos.</span><span class="sxs-lookup"><span data-stu-id="78629-103">*Thread pooling* is a form of multithreading in which tasks are added to a queue and automatically started when threads are created.</span></span> <span data-ttu-id="78629-104">Para obtener más información, vea [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) (Agrupación de subprocesos [C#]).</span><span class="sxs-lookup"><span data-stu-id="78629-104">For more information, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).</span></span>  
  
 <span data-ttu-id="78629-105">En el ejemplo siguiente se usa el grupo de subprocesos de .NET Framework para calcular el resultado de `Fibonacci` para diez números entre 20 y 40.</span><span class="sxs-lookup"><span data-stu-id="78629-105">The following example uses the .NET Framework thread pool to calculate the `Fibonacci` result for ten numbers between 20 and 40.</span></span> <span data-ttu-id="78629-106">Cada resultado de `Fibonacci` se representa mediante la clase `Fibonacci`, que proporciona un método denominado `ThreadPoolCallback` que realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="78629-106">Each `Fibonacci` result is represented by the `Fibonacci` class, which provides a method named `ThreadPoolCallback` that performs the calculation.</span></span> <span data-ttu-id="78629-107">Se crea un objeto que representa cada valor de `Fibonacci` y el método `ThreadPoolCallback` se pasa a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, que asigna un subproceso disponible en el grupo para ejecutar el método.</span><span class="sxs-lookup"><span data-stu-id="78629-107">An object that represents each `Fibonacci` value is created, and the `ThreadPoolCallback` method is passed to <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, which assigns an available thread in the pool to execute the method.</span></span>  
  
 <span data-ttu-id="78629-108">Dado que a cada objeto `Fibonacci` se le asigna un valor semialeatorio para calcular y dado que cada subproceso compite para obtener tiempo de procesador, no se puede saber de antemano cuánto tardarán en calcularse los diez resultados.</span><span class="sxs-lookup"><span data-stu-id="78629-108">Because each `Fibonacci` object is given a semi-random value to compute, and because each thread will be competing for processor time, you cannot know in advance how long it will take for all ten results to be calculated.</span></span> <span data-ttu-id="78629-109">Por eso se pasa a cada objeto `Fibonacci` una instancia de la clase <xref:System.Threading.ManualResetEvent> durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="78629-109">That is why each `Fibonacci` object is passed an instance of the <xref:System.Threading.ManualResetEvent> class during construction.</span></span> <span data-ttu-id="78629-110">Cada objeto indica al objeto de evento proporcionado que su cálculo está completo, lo que permite que el subproceso principal bloquee la ejecución con <xref:System.Threading.WaitHandle.WaitAll%2A> hasta que los diez objetos `Fibonacci` hayan calculado un resultado.</span><span class="sxs-lookup"><span data-stu-id="78629-110">Each object signals the provided event object when its calculation is complete, which allows the primary thread to block execution with <xref:System.Threading.WaitHandle.WaitAll%2A> until all ten `Fibonacci` objects have calculated a result.</span></span> <span data-ttu-id="78629-111">El método `Main` muestra entonces cada resultado de `Fibonacci`.</span><span class="sxs-lookup"><span data-stu-id="78629-111">The `Main` method then displays each `Fibonacci` result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78629-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78629-112">Example</span></span>  
  
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
  
 <span data-ttu-id="78629-113">El siguiente es un ejemplo de la salida.</span><span class="sxs-lookup"><span data-stu-id="78629-113">Following is an example of the output.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="78629-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="78629-114">See Also</span></span>  
 <span data-ttu-id="78629-115"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="78629-115"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="78629-116"><xref:System.Threading.WaitHandle.WaitAll%2A></span><span class="sxs-lookup"><span data-stu-id="78629-116"><xref:System.Threading.WaitHandle.WaitAll%2A></span></span>   
 <span data-ttu-id="78629-117"><xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="78629-117"><xref:System.Threading.ManualResetEvent></span></span>   
 <span data-ttu-id="78629-118"><xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="78629-118"><xref:System.Threading.EventWaitHandle.Set%2A></span></span>   
 <span data-ttu-id="78629-119"><xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="78629-119"><xref:System.Threading.ThreadPool></span></span>   
 <span data-ttu-id="78629-120"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="78629-120"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="78629-121"><xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="78629-121"><xref:System.Threading.ManualResetEvent></span></span>   
 <span data-ttu-id="78629-122">[Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  (Agrupación de subprocesos [C#])</span><span class="sxs-lookup"><span data-stu-id="78629-122">[Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
 <span data-ttu-id="78629-123">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  (Subprocesos [C#])</span><span class="sxs-lookup"><span data-stu-id="78629-123">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span></span>  
 <span data-ttu-id="78629-124">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="78629-124">@System.Threading.Monitor</span></span>   
 [<span data-ttu-id="78629-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="78629-125">Security</span></span>](../../../../standard/security/index.md)

