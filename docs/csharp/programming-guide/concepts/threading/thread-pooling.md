---
title: Agrupación de subprocesos (C#)
ms.date: 07/20/2015
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
ms.openlocfilehash: 42e1dcedc1897dc82bbd13f12882cbef6a5da4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="thread-pooling-c"></a><span data-ttu-id="9d110-102">Agrupación de subprocesos (C#)</span><span class="sxs-lookup"><span data-stu-id="9d110-102">Thread Pooling (C#)</span></span>
<span data-ttu-id="9d110-103">Un *grupo de subprocesos* es una colección de subprocesos que puede usarse para realizar varias tareas en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9d110-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="9d110-104">(Vea [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) (Subprocesos (C#)) para obtener información general). Esto deja libre el subproceso primario para realizar otras tareas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9d110-104">(See [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="9d110-105">Los grupos de subprocesos suelen emplearse en aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="9d110-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="9d110-106">Cada solicitud entrante se asigna a un subproceso del grupo de subprocesos, de modo que la solicitud se pueda procesar de forma asincrónica, sin acaparar el subproceso primario ni retrasar el procesamiento de solicitudes posteriores.</span><span class="sxs-lookup"><span data-stu-id="9d110-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="9d110-107">Una vez que un subproceso del grupo finaliza su tarea, se devuelve a una cola de subprocesos en espera, donde se puede reutilizar.</span><span class="sxs-lookup"><span data-stu-id="9d110-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="9d110-108">Esta reutilización permite que las aplicaciones eviten el costo que significa crear un nuevo subproceso para cada tarea.</span><span class="sxs-lookup"><span data-stu-id="9d110-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="9d110-109">Normalmente, los grupos de subprocesos tienen un número máximo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9d110-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="9d110-110">Si todos los subprocesos están ocupados, las tareas adicionales se colocan en cola hasta que se puedan atender a medida que estén disponibles los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9d110-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="9d110-111">Puede implementar su propio grupo de subprocesos, pero es más fácil usar el grupo de subprocesos proporcionado por .NET Framework a través de la clase <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="9d110-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="9d110-112">Con la agrupación de subprocesos, se llama al método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> con un delegado para el procedimiento que se quiere ejecutar, y C# crea el subproceso y ejecuta el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d110-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and C# creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="9d110-113">Ejemplo de agrupación de subprocesos</span><span class="sxs-lookup"><span data-stu-id="9d110-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="9d110-114">En el ejemplo siguiente se muestra cómo se puede usar la agrupación de subprocesos para iniciar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="9d110-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 <span data-ttu-id="9d110-115">Una ventaja de la agrupación de subprocesos es que se pueden pasar argumentos de un objeto de estado al procedimiento de tarea.</span><span class="sxs-lookup"><span data-stu-id="9d110-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="9d110-116">Si el procedimiento al que se está llamando requiere más de un argumento, puede convertir una estructura o una instancia de una clase en un tipo de datos `Object`.</span><span class="sxs-lookup"><span data-stu-id="9d110-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="9d110-117">Parámetros y valores devueltos de grupos de subprocesos</span><span class="sxs-lookup"><span data-stu-id="9d110-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="9d110-118">La devolución de valores desde un subproceso del grupo de subprocesos no es sencilla.</span><span class="sxs-lookup"><span data-stu-id="9d110-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="9d110-119">La manera estándar de devolver valores desde una llamada de función no está permitida, ya que los procedimientos `Sub` son el único tipo de procedimiento que se puede poner en cola en un grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9d110-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="9d110-120">Una manera de proporcionar parámetros y valores devueltos consiste en empaquetar los parámetros, los valores devueltos y los métodos en una clase contenedora, como se describe en [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) (Parámetros y valores devueltos para procedimientos multiproceso (C#)).</span><span class="sxs-lookup"><span data-stu-id="9d110-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="9d110-121">Una manera más sencilla de proporcionar parámetros y devolver valores es usar la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d110-121">An easier way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="9d110-122">Si usa esta variable para pasar una referencia a una instancia de una clase, el subproceso del grupo de subprocesos puede modificar los miembros de la instancia y estos pueden usarse como valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="9d110-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="9d110-123">A primera vista, probablemente no sea obvio que se puede modificar un objeto al que hace referencia una variable que se pasa por valor.</span><span class="sxs-lookup"><span data-stu-id="9d110-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="9d110-124">Esto se puede hacer porque solo se pasa por valor la referencia del objeto.</span><span class="sxs-lookup"><span data-stu-id="9d110-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="9d110-125">Cuando se realizan cambios en los miembros del objeto al que hace referencia la referencia de objeto, los cambios se aplican a la instancia de clase real.</span><span class="sxs-lookup"><span data-stu-id="9d110-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="9d110-126">Las estructuras no se pueden usar para devolver valores dentro de objetos de estado.</span><span class="sxs-lookup"><span data-stu-id="9d110-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="9d110-127">Dado que las estructuras son tipos de valor, los cambios que realiza el proceso asincrónico no cambian los miembros de la estructura original.</span><span class="sxs-lookup"><span data-stu-id="9d110-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="9d110-128">Use estructuras para proporcionar parámetros cuando no se necesiten valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="9d110-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d110-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d110-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="9d110-130">Cómo: Usar un grupo de subprocesos (C#)</span><span class="sxs-lookup"><span data-stu-id="9d110-130">How to: Use a Thread Pool (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [<span data-ttu-id="9d110-131">Subprocesamiento (C#)</span><span class="sxs-lookup"><span data-stu-id="9d110-131">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="9d110-132">Aplicaciones multiproceso (C#)</span><span class="sxs-lookup"><span data-stu-id="9d110-132">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="9d110-133">Sincronización de subprocesos (C#)</span><span class="sxs-lookup"><span data-stu-id="9d110-133">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
