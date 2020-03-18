---
title: Procedimientos recomendados para el subprocesamiento administrado
ms.date: 10/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: a76cc40f308ac2f636a650cd4a17da0e94e23a34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160266"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="d46e9-102">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="d46e9-102">Managed threading best practices</span></span>
<span data-ttu-id="d46e9-103">El multithreading requiere que la programación sea cuidadosa.</span><span class="sxs-lookup"><span data-stu-id="d46e9-103">Multithreading requires careful programming.</span></span> <span data-ttu-id="d46e9-104">La complejidad de muchas tareas se puede reducir poniendo las solicitudes de ejecución en cola por subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-104">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="d46e9-105">En este tema se tratan situaciones más complicadas, como coordinar el trabajo de múltiples subprocesos, o controlar los subprocesos que se bloquean.</span><span class="sxs-lookup"><span data-stu-id="d46e9-105">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d46e9-106">A partir de NET Framework 4, la biblioteca TPL y PLINQ proporcionan API que reducen parte de la complejidad y los riesgos que entraña la programación multiproceso.</span><span class="sxs-lookup"><span data-stu-id="d46e9-106">Starting with the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="d46e9-107">Para más información, consulte [Programación en paralelo en .NET](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="d46e9-107">For more information, see [Parallel Programming in .NET](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="d46e9-108">Interbloqueos y condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="d46e9-108">Deadlocks and race conditions</span></span>  
 <span data-ttu-id="d46e9-109">El multithreading resuelve problemas de rendimiento y de capacidad de respuesta, pero al hacerlo también crea nuevos problemas, como interbloqueos y condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="d46e9-109">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="d46e9-110">Interbloqueos</span><span class="sxs-lookup"><span data-stu-id="d46e9-110">Deadlocks</span></span>  
 <span data-ttu-id="d46e9-111">Un interbloqueo tiene lugar cuando dos subprocesos intentan bloquear un recurso que ya ha bloqueado uno de estos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-111">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="d46e9-112">Ninguno de los subprocesos puede avanzar.</span><span class="sxs-lookup"><span data-stu-id="d46e9-112">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="d46e9-113">Muchos métodos de las clases del subprocesamiento administrado ofrecen tiempos de espera que se utilizan para detectar interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-113">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="d46e9-114">Por ejemplo, con el siguiente código se intenta obtener un bloqueo en un objeto llamado `lockObject`.</span><span class="sxs-lookup"><span data-stu-id="d46e9-114">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="d46e9-115">Si el bloqueo no se consigue en 300 milisegundos, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> devuelve el valor `false`.</span><span class="sxs-lookup"><span data-stu-id="d46e9-115">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a><span data-ttu-id="d46e9-116">Condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="d46e9-116">Race conditions</span></span>  
 <span data-ttu-id="d46e9-117">Una condición de carrera es un error que se produce cuando el resultado de un programa depende del primero de dos o más subprocesos que consiga llegar hasta un bloque específico de código.</span><span class="sxs-lookup"><span data-stu-id="d46e9-117">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="d46e9-118">Ejecutar el programa muchas veces genera distintos resultados y no es posible predecir el resultado de una ejecución específica.</span><span class="sxs-lookup"><span data-stu-id="d46e9-118">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="d46e9-119">Un ejemplo sencillo de una condición de carrera es el incremento de un campo.</span><span class="sxs-lookup"><span data-stu-id="d46e9-119">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="d46e9-120">Suponga una clase que tiene un campo privado **static** (**Shared** en Visual Basic) que se incrementa cada vez que se crea una instancia de la clase, mediante código como `objCt++;` (C#) o `objCt += 1` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d46e9-120">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="d46e9-121">Esta operación requiere cargar el valor de `objCt` en un registro, incrementar el valor y almacenarlo en `objCt`.</span><span class="sxs-lookup"><span data-stu-id="d46e9-121">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="d46e9-122">En una aplicación multiproceso, un subproceso que realiza los tres pasos puede adelantar al subproceso que ha cargado e incrementado el valor; cuando el primer subproceso reanuda la ejecución y almacena su valor, sobrescribe `objCt` sin tener en cuenta el hecho de que el valor ha cambiado mientras tanto.</span><span class="sxs-lookup"><span data-stu-id="d46e9-122">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="d46e9-123">Para evitar fácilmente esta condición de carrera determinada, utilice los métodos de la clase <xref:System.Threading.Interlocked>, como <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d46e9-123">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d46e9-124">Para más información sobre otras técnicas de sincronización de datos entre varios subprocesos, consulte [Sincronización de datos para multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span><span class="sxs-lookup"><span data-stu-id="d46e9-124">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="d46e9-125">También se pueden producir condiciones de carrera al sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-125">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="d46e9-126">Siempre que escriba una línea de código, debe tener en cuenta qué puede ocurrir si otro subproceso adelanta a un subproceso antes de ejecutar la línea (o antes de cualquiera de las instrucciones máquina que forman la línea).</span><span class="sxs-lookup"><span data-stu-id="d46e9-126">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="d46e9-127">Miembros estáticos y constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="d46e9-127">Static members and static constructors</span></span>  
 <span data-ttu-id="d46e9-128">No se inicializa una clase hasta que su constructor de clase (constructor`static` en C#, `Shared Sub New` en Visual Basic) haya terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d46e9-128">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="d46e9-129">Para evitar la ejecución de código en un tipo no inicializado, Common Language Runtime bloquea todas las llamadas de otros subprocesos a los miembros `static` de la clase (miembros`Shared` en Visual Basic) hasta que el constructor de clase termina de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d46e9-129">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="d46e9-130">Por ejemplo, si un constructor de clase inicia un nuevo subproceso, y el procedimiento del subproceso llama a un miembro `static` de la clase, el nuevo subproceso se bloquea hasta que el constructor de clase finalice.</span><span class="sxs-lookup"><span data-stu-id="d46e9-130">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="d46e9-131">Esto se aplica a cualquier tipo que pueda tener un constructor `static`.</span><span class="sxs-lookup"><span data-stu-id="d46e9-131">This applies to any type that can have a `static` constructor.</span></span>  

## <a name="number-of-processors"></a><span data-ttu-id="d46e9-132">Número de procesadores</span><span class="sxs-lookup"><span data-stu-id="d46e9-132">Number of processors</span></span>

<span data-ttu-id="d46e9-133">Si hay varios procesadores o uno solo disponibles en un sistema puede influir en la arquitectura de multiproceso.</span><span class="sxs-lookup"><span data-stu-id="d46e9-133">Whether there are multiple processors or only one processor available on a system can influence multithreaded architecture.</span></span> <span data-ttu-id="d46e9-134">Para obtener más información, vea [Número de procesadores](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span><span class="sxs-lookup"><span data-stu-id="d46e9-134">For more information, see [Number of Processors](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span></span>

<span data-ttu-id="d46e9-135">Use la propiedad <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> para determinar el número de procesadores disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d46e9-135">Use the <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> property to determine the number of processors available at runtime.</span></span>
  
## <a name="general-recommendations"></a><span data-ttu-id="d46e9-136">Recomendaciones generales</span><span class="sxs-lookup"><span data-stu-id="d46e9-136">General recommendations</span></span>  
 <span data-ttu-id="d46e9-137">Tenga en cuenta las siguientes instrucciones cuando utilice varios subprocesos:</span><span class="sxs-lookup"><span data-stu-id="d46e9-137">Consider the following guidelines when using multiple threads:</span></span>  
  
- <span data-ttu-id="d46e9-138">No utilice <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para finalizar otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-138">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="d46e9-139">Una llamada a **Abort** en otro subproceso es similar a iniciar una excepción en ese subproceso, sin conocer qué punto ha alcanzado en su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d46e9-139">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
- <span data-ttu-id="d46e9-140">No utilice <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-140">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="d46e9-141">Utilice <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="d46e9-141">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
- <span data-ttu-id="d46e9-142">No controle la ejecución de subprocesos de trabajo desde el programa principal (con eventos, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="d46e9-142">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="d46e9-143">En su lugar, diseñe un programa de forma que los subprocesos de trabajo sean los que tengan que esperar hasta que haya trabajo disponible, lo ejecuten y notifiquen su finalización a otras partes del programa.</span><span class="sxs-lookup"><span data-stu-id="d46e9-143">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="d46e9-144">Si los subprocesos de trabajo no se bloquean, puede ser conveniente usar subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-144">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="d46e9-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> resulta útil en aquellas situaciones en las que los subprocesos de trabajo se bloquean.</span><span class="sxs-lookup"><span data-stu-id="d46e9-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
- <span data-ttu-id="d46e9-146">No utilice los tipos como objetos de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d46e9-146">Don't use types as lock objects.</span></span> <span data-ttu-id="d46e9-147">Es decir, evite código como `lock(typeof(X))` en C# o `SyncLock(GetType(X))` en Visual Basic o el uso de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> con objetos <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d46e9-147">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="d46e9-148">Para un tipo determinado, hay sólo una instancia de <xref:System.Type?displayProperty=nameWithType> por el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d46e9-148">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="d46e9-149">Si el tipo que quiere bloquear es público, codifique uno que su tipo no pueda bloquear, para evitar interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-149">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="d46e9-150">Para otros problemas, consulte [Procedimientos recomendados para la confiabilidad](../../../docs/framework/performance/reliability-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="d46e9-150">For additional issues, see [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md).</span></span>  
  
- <span data-ttu-id="d46e9-151">Tenga cuidado al efectuar bloqueos en instancias, por ejemplo `lock(this)` en C# o `SyncLock(Me)` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d46e9-151">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="d46e9-152">Si otra parte del código de la aplicación, ajeno al tipo, bloquea el objeto, podrían producirse interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-152">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
- <span data-ttu-id="d46e9-153">Asegúrese de que un subproceso que entra en un monitor siempre sale de ese monitor, aun en el caso de que se produzca una excepción mientras el subproceso se encuentra en el monitor.</span><span class="sxs-lookup"><span data-stu-id="d46e9-153">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="d46e9-154">La instrucción [lock](../../csharp/language-reference/keywords/lock-statement.md) de C# y la instrucción [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) de Visual Basic ofrecen automáticamente este comportamiento mediante un bloque **finally** que garantiza la llamada a <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d46e9-154">The C# [lock](../../csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="d46e9-155">Si no está seguro de que se llamará a **Exit**, considere la posibilidad de cambiar el diseño con el fin de usar **Mutex**.</span><span class="sxs-lookup"><span data-stu-id="d46e9-155">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="d46e9-156">Una zona de exclusión mutua se libera automáticamente cuando finaliza el subproceso al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="d46e9-156">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
- <span data-ttu-id="d46e9-157">Utilice varios subprocesos para tareas que requieren recursos diferentes, y evite asignar varios subprocesos a un solo recurso.</span><span class="sxs-lookup"><span data-stu-id="d46e9-157">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="d46e9-158">Por ejemplo, en tareas que impliquen beneficios de E/S por tener un subproceso propio, ya que ese subproceso se bloquea durante las operaciones de E/S y, de este modo, permite ejecutar otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-158">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="d46e9-159">Los datos proporcionados por el usuario son otro recurso que se beneficia de la utilización de un subproceso dedicado.</span><span class="sxs-lookup"><span data-stu-id="d46e9-159">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="d46e9-160">En un equipo de un solo procesador, una tarea que implica un cálculo intensivo coexiste con los datos proporcionados por el usuario y con tareas que implican la E/S, pero varias tareas de cálculo intensivo compiten entre ellas.</span><span class="sxs-lookup"><span data-stu-id="d46e9-160">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
- <span data-ttu-id="d46e9-161">Considere la posibilidad de utilizar métodos de la clase <xref:System.Threading.Interlocked> para los cambios de estado simples, en lugar de utilizar la instrucción `lock` (`SyncLock` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d46e9-161">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="d46e9-162">La instrucción `lock` es una buena herramienta de uso general, pero la clase <xref:System.Threading.Interlocked> genera mejor rendimiento para las actualizaciones que deben ser atómicas.</span><span class="sxs-lookup"><span data-stu-id="d46e9-162">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="d46e9-163">Internamente, ejecuta un solo prefijo de bloqueo si no hay contención.</span><span class="sxs-lookup"><span data-stu-id="d46e9-163">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="d46e9-164">En las revisiones de código, inspeccione código similar al que se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d46e9-164">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="d46e9-165">En el primer ejemplo, se incrementa una variable de estado:</span><span class="sxs-lookup"><span data-stu-id="d46e9-165">In the first example, a state variable is incremented:</span></span>  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)
    {  
        myField++;  
    }  
    ```  
  
     <span data-ttu-id="d46e9-166">Para mejorar el rendimiento, utilice el método <xref:System.Threading.Interlocked.Increment%2A> en lugar de la instrucción `lock`, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d46e9-166">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="d46e9-167">En .NET Framework 2.0 y versiones posteriores, use el método <xref:System.Threading.Interlocked.Add%2A> para incrementos atómicos mayores que 1.</span><span class="sxs-lookup"><span data-stu-id="d46e9-167">In the .NET Framework 2.0 and later, use the <xref:System.Threading.Interlocked.Add%2A> method for atomic increments larger than 1.</span></span>  
  
     <span data-ttu-id="d46e9-168">En el segundo ejemplo, se actualiza una variable de tipo de referencia sólo si es una referencia nula (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d46e9-168">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            x ??= y;
        }  
    }  
    ```  
  
     <span data-ttu-id="d46e9-169">Se puede mejorar el rendimiento utilizando el método <xref:System.Threading.Interlocked.CompareExchange%2A> de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d46e9-169">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="d46e9-170">A partir de .NET Framework 2.0, la sobrecarga del método <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> proporciona una alternativa de seguridad de tipos para tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d46e9-170">Beginning with .NET Framework 2.0, the <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> method overload provides a type-safe alternative for reference types.</span></span>
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="d46e9-171">Recomendaciones para las bibliotecas de clases</span><span class="sxs-lookup"><span data-stu-id="d46e9-171">Recommendations for class libraries</span></span>  
 <span data-ttu-id="d46e9-172">Tenga en cuenta las instrucciones siguientes cuando diseñe bibliotecas de clases para el multithreading:</span><span class="sxs-lookup"><span data-stu-id="d46e9-172">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
- <span data-ttu-id="d46e9-173">Evite la necesidad de sincronización si es posible.</span><span class="sxs-lookup"><span data-stu-id="d46e9-173">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="d46e9-174">Esto se aplica especialmente en el caso de código muy utilizado.</span><span class="sxs-lookup"><span data-stu-id="d46e9-174">This is especially true for heavily used code.</span></span> <span data-ttu-id="d46e9-175">Por ejemplo, se podría ajustar un algoritmo de modo que tolere una condición de carrera en lugar de eliminarla.</span><span class="sxs-lookup"><span data-stu-id="d46e9-175">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="d46e9-176">La sincronización innecesaria disminuye el rendimiento y crea la posibilidad de interbloqueos y condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="d46e9-176">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
- <span data-ttu-id="d46e9-177">Procure que los datos estáticos (`Shared` en Visual Basic) sean seguros para subprocesos de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d46e9-177">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
- <span data-ttu-id="d46e9-178">No convierta los datos de instancia en datos seguros para subprocesos de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d46e9-178">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="d46e9-179">Al agregar bloqueos para crear código seguro para subprocesos, se reduce el rendimiento, se incrementa la contención de bloqueos y se crea la posibilidad de que se produzcan interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-179">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="d46e9-180">En los modelos de aplicación comunes, sólo un subproceso a la vez ejecuta código de usuario, lo que minimiza la necesidad de la seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-180">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="d46e9-181">Por esta razón, las bibliotecas de clases de .NET Framework no son seguras para subprocesos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d46e9-181">For this reason, the .NET Framework class libraries are not thread safe by default.</span></span>  
  
- <span data-ttu-id="d46e9-182">Evite proporcionar métodos estáticos que alteren el estado estático.</span><span class="sxs-lookup"><span data-stu-id="d46e9-182">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="d46e9-183">En escenarios de servidor comunes, el estado estático se comparte entre las solicitudes, lo que significa que varios subprocesos pueden ejecutar a la vez ese código.</span><span class="sxs-lookup"><span data-stu-id="d46e9-183">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="d46e9-184">De este modo, se abre la posibilidad de errores de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d46e9-184">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="d46e9-185">Considere la posibilidad de utilizar un modelo de diseño que encapsule los datos en instancias no compartidas por las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d46e9-185">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="d46e9-186">Además, si se sincronizan los datos estáticos, las llamadas entre los métodos estáticos que modifican el estado pueden generar interbloqueos o sincronización redundante, lo que afecta negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d46e9-186">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46e9-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="d46e9-187">See also</span></span>

- [<span data-ttu-id="d46e9-188">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="d46e9-188">Threading</span></span>](../../../docs/standard/threading/index.md)
- [<span data-ttu-id="d46e9-189">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="d46e9-189">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)
