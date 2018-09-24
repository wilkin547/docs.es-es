---
title: Procedimientos recomendados para el subprocesamiento administrado
ms.date: 11/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f95fb3ccab7362021a7a195ea199a1370e003dd2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562377"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="ceed1-102">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="ceed1-102">Managed Threading Best Practices</span></span>
<span data-ttu-id="ceed1-103">El multithreading requiere que la programación sea cuidadosa.</span><span class="sxs-lookup"><span data-stu-id="ceed1-103">Multithreading requires careful programming.</span></span> <span data-ttu-id="ceed1-104">La complejidad de muchas tareas se puede reducir poniendo las solicitudes de ejecución en cola por subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-104">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="ceed1-105">En este tema se tratan situaciones más complicadas, como coordinar el trabajo de múltiples subprocesos, o controlar los subprocesos que se bloquean.</span><span class="sxs-lookup"><span data-stu-id="ceed1-105">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ceed1-106">A partir de NET Framework 4, la biblioteca TPL y PLINQ proporcionan API que reducen parte de la complejidad y los riesgos que entraña la programación multiproceso.</span><span class="sxs-lookup"><span data-stu-id="ceed1-106">Starting with the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="ceed1-107">Para más información, consulte [Programación en paralelo en .NET](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="ceed1-107">For more information, see [Parallel Programming in .NET](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="ceed1-108">Interbloqueos y condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="ceed1-108">Deadlocks and Race Conditions</span></span>  
 <span data-ttu-id="ceed1-109">El multithreading resuelve problemas de rendimiento y de capacidad de respuesta, pero al hacerlo también crea nuevos problemas, como interbloqueos y condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="ceed1-109">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="ceed1-110">Interbloqueos</span><span class="sxs-lookup"><span data-stu-id="ceed1-110">Deadlocks</span></span>  
 <span data-ttu-id="ceed1-111">Un interbloqueo tiene lugar cuando dos subprocesos intentan bloquear un recurso que ya ha bloqueado uno de estos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-111">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="ceed1-112">Ninguno de los subprocesos puede avanzar.</span><span class="sxs-lookup"><span data-stu-id="ceed1-112">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="ceed1-113">Muchos métodos de las clases del subprocesamiento administrado ofrecen tiempos de espera que se utilizan para detectar interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-113">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="ceed1-114">Por ejemplo, con el siguiente código se intenta obtener un bloqueo en un objeto llamado `lockObject`.</span><span class="sxs-lookup"><span data-stu-id="ceed1-114">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="ceed1-115">Si el bloqueo no se consigue en 300 milisegundos, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> devuelve el valor `false`.</span><span class="sxs-lookup"><span data-stu-id="ceed1-115">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
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
  
### <a name="race-conditions"></a><span data-ttu-id="ceed1-116">Condiciones de carrera</span><span class="sxs-lookup"><span data-stu-id="ceed1-116">Race Conditions</span></span>  
 <span data-ttu-id="ceed1-117">Una condición de carrera es un error que se produce cuando el resultado de un programa depende del primero de dos o más subprocesos que consiga llegar hasta un bloque específico de código.</span><span class="sxs-lookup"><span data-stu-id="ceed1-117">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="ceed1-118">Ejecutar el programa muchas veces genera distintos resultados y no es posible predecir el resultado de una ejecución específica.</span><span class="sxs-lookup"><span data-stu-id="ceed1-118">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="ceed1-119">Un ejemplo sencillo de una condición de carrera es el incremento de un campo.</span><span class="sxs-lookup"><span data-stu-id="ceed1-119">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="ceed1-120">Suponga una clase que tiene un campo privado **static** (**Shared** en Visual Basic) que se incrementa cada vez que se crea una instancia de la clase, mediante código como `objCt++;` (C#) o `objCt += 1` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ceed1-120">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="ceed1-121">Esta operación requiere cargar el valor de `objCt` en un registro, incrementar el valor y almacenarlo en `objCt`.</span><span class="sxs-lookup"><span data-stu-id="ceed1-121">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="ceed1-122">En una aplicación multiproceso, un subproceso que realiza los tres pasos puede adelantar al subproceso que ha cargado e incrementado el valor; cuando el primer subproceso reanuda la ejecución y almacena su valor, sobrescribe `objCt` sin tener en cuenta el hecho de que el valor ha cambiado mientras tanto.</span><span class="sxs-lookup"><span data-stu-id="ceed1-122">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="ceed1-123">Para evitar fácilmente esta condición de carrera determinada, utilice los métodos de la clase <xref:System.Threading.Interlocked>, como <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ceed1-123">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ceed1-124">Para más información sobre otras técnicas de sincronización de datos entre varios subprocesos, consulte [Sincronización de datos para multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span><span class="sxs-lookup"><span data-stu-id="ceed1-124">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="ceed1-125">También se pueden producir condiciones de carrera al sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-125">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="ceed1-126">Siempre que escriba una línea de código, debe tener en cuenta qué puede ocurrir si otro subproceso adelanta a un subproceso antes de ejecutar la línea (o antes de cualquiera de las instrucciones máquina que forman la línea).</span><span class="sxs-lookup"><span data-stu-id="ceed1-126">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="number-of-processors"></a><span data-ttu-id="ceed1-127">Número de procesadores</span><span class="sxs-lookup"><span data-stu-id="ceed1-127">Number of Processors</span></span>  
 <span data-ttu-id="ceed1-128">La mayoría de los equipos tienen ahora varios procesadores (también llamados núcleos), incluso los pequeños dispositivos como tabletas y teléfonos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-128">Most computers now have multiple processors (also called cores), even small devices such as tablets and phones.</span></span> <span data-ttu-id="ceed1-129">Si está desarrollando software que también se ejecutará en equipos con un solo procesador, tenga en cuenta que el multithreading resuelve distintos problemas en equipos con varios procesadores y en equipos con un solo procesador.</span><span class="sxs-lookup"><span data-stu-id="ceed1-129">If you know you're developing software that will also run on single-processor computers, you should be aware that multithreading solves different problems for single-processor computers and multiprocessor computers.</span></span>  
  
### <a name="multiprocessor-computers"></a><span data-ttu-id="ceed1-130">Equipos multiprocesador</span><span class="sxs-lookup"><span data-stu-id="ceed1-130">Multiprocessor Computers</span></span>  
 <span data-ttu-id="ceed1-131">El multithreading proporciona un mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ceed1-131">Multithreading provides greater throughput.</span></span> <span data-ttu-id="ceed1-132">Diez procesadores pueden hacer diez veces el trabajo de uno, pero sólo si el trabajo se divide de forma que los diez trabajen al mismo tiempo; los subprocesos proporcionan una forma fácil de dividir el trabajo y de aprovechar la eficacia de procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="ceed1-132">Ten processors can do ten times the work of one, but only if the work is divided so that all ten can be working at once; threads provide an easy way to divide the work and exploit the extra processing power.</span></span> <span data-ttu-id="ceed1-133">Si utiliza el multithreading en un equipo multiprocesador:</span><span class="sxs-lookup"><span data-stu-id="ceed1-133">If you use multithreading on a multiprocessor computer:</span></span>  
  
-   <span data-ttu-id="ceed1-134">El número de subprocesos que se pueden ejecutar de forma simultánea está limitado por el número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="ceed1-134">The number of threads that can execute concurrently is limited by the number of processors.</span></span>  
  
-   <span data-ttu-id="ceed1-135">Sólo se ejecuta un subproceso en segundo plano si el número de subprocesos que se ejecutan en primer plano es menor que el número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="ceed1-135">A background thread executes only when the number of foreground threads executing is smaller than the number of processors.</span></span>  
  
-   <span data-ttu-id="ceed1-136">Cuando se llama al método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> en un subproceso, ese subproceso se puede ejecutar o no inmediatamente dependiendo del número de procesadores y de subprocesos en espera de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ceed1-136">When you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method on a thread, that thread might or might not start executing immediately, depending on the number of processors and the number of threads currently waiting to execute.</span></span>  
  
-   <span data-ttu-id="ceed1-137">Las condiciones de carrera se pueden producir no sólo debido a las prioridades imprevistas de subprocesos, sino también porque dos subprocesos que se ejecutan en procesadores diferentes pueden competir para alcanzar el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="ceed1-137">Race conditions can occur not only because threads are preempted unexpectedly, but because two threads executing on different processors might be racing to reach the same code block.</span></span>  
  
### <a name="single-processor-computers"></a><span data-ttu-id="ceed1-138">Equipos de un solo procesador</span><span class="sxs-lookup"><span data-stu-id="ceed1-138">Single-Processor Computers</span></span>  
 <span data-ttu-id="ceed1-139">El multithreading ofrece una gran capacidad de respuesta al usuario del equipo, y utiliza el tiempo de inactividad para realizar tareas en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ceed1-139">Multithreading provides greater responsiveness to the computer user, and uses idle time for background tasks.</span></span> <span data-ttu-id="ceed1-140">Si utiliza el multithreading en un equipo de un solo procesador:</span><span class="sxs-lookup"><span data-stu-id="ceed1-140">If you use multithreading on a single-processor computer:</span></span>  
  
-   <span data-ttu-id="ceed1-141">Sólo se ejecuta un subproceso cada vez.</span><span class="sxs-lookup"><span data-stu-id="ceed1-141">Only one thread runs at any instant.</span></span>  
  
-   <span data-ttu-id="ceed1-142">Se ejecuta un subproceso en segundo plano sólo cuando el subproceso principal del usuario está inactivo.</span><span class="sxs-lookup"><span data-stu-id="ceed1-142">A background thread executes only when the main user thread is idle.</span></span> <span data-ttu-id="ceed1-143">Un subproceso en primer plano que se ejecuta continuamente agota el tiempo de procesador de los subprocesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ceed1-143">A foreground thread that executes constantly starves background threads of processor time.</span></span>  
  
-   <span data-ttu-id="ceed1-144">Cuando se llama al método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> en un subproceso, ese subproceso no se ejecuta hasta que el subproceso en curso le cede la ejecución o es relegado por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ceed1-144">When you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method on a thread, that thread does not start executing until the current thread yields or is preempted by the operating system.</span></span>  
  
-   <span data-ttu-id="ceed1-145">Generalmente, las condiciones de carrera se producen debido a que el programador no tuvo en cuenta el hecho de que un subproceso puede ser adelantado por otro en un momento difícil permitiendo, algunas veces, que otro subproceso llegue el primero al bloque de código.</span><span class="sxs-lookup"><span data-stu-id="ceed1-145">Race conditions typically occur because the programmer did not anticipate the fact that a thread can be preempted at an awkward moment, sometimes allowing another thread to reach a code block first.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="ceed1-146">Miembros estáticos y constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="ceed1-146">Static Members and Static Constructors</span></span>  
 <span data-ttu-id="ceed1-147">No se inicializa una clase hasta que su constructor de clase (constructor`static` en C#, `Shared Sub New` en Visual Basic) haya terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ceed1-147">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="ceed1-148">Para evitar la ejecución de código en un tipo no inicializado, Common Language Runtime bloquea todas las llamadas de otros subprocesos a los miembros `static` de la clase (miembros`Shared` en Visual Basic) hasta que el constructor de clase termina de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ceed1-148">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="ceed1-149">Por ejemplo, si un constructor de clase inicia un nuevo subproceso, y el procedimiento del subproceso llama a un miembro `static` de la clase, el nuevo subproceso se bloquea hasta que el constructor de clase finalice.</span><span class="sxs-lookup"><span data-stu-id="ceed1-149">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="ceed1-150">Esto se aplica a cualquier tipo que pueda tener un constructor `static`.</span><span class="sxs-lookup"><span data-stu-id="ceed1-150">This applies to any type that can have a `static` constructor.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="ceed1-151">Recomendaciones generales</span><span class="sxs-lookup"><span data-stu-id="ceed1-151">General Recommendations</span></span>  
 <span data-ttu-id="ceed1-152">Tenga en cuenta las siguientes instrucciones cuando utilice varios subprocesos:</span><span class="sxs-lookup"><span data-stu-id="ceed1-152">Consider the following guidelines when using multiple threads:</span></span>  
  
-   <span data-ttu-id="ceed1-153">No utilice <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para finalizar otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-153">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="ceed1-154">Una llamada a **Abort** en otro subproceso es similar a iniciar una excepción en ese subproceso, sin conocer qué punto ha alcanzado en su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ceed1-154">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
-   <span data-ttu-id="ceed1-155">No utilice <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-155">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="ceed1-156">Utilice <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="ceed1-156">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
-   <span data-ttu-id="ceed1-157">No controle la ejecución de subprocesos de trabajo desde el programa principal (con eventos, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ceed1-157">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="ceed1-158">En su lugar, diseñe un programa de forma que los subprocesos de trabajo sean los que tengan que esperar hasta que haya trabajo disponible, lo ejecuten y notifiquen su finalización a otras partes del programa.</span><span class="sxs-lookup"><span data-stu-id="ceed1-158">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="ceed1-159">Si los subprocesos de trabajo no se bloquean, puede ser conveniente usar subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-159">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="ceed1-160"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> resulta útil en aquellas situaciones en las que los subprocesos de trabajo se bloquean.</span><span class="sxs-lookup"><span data-stu-id="ceed1-160"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
-   <span data-ttu-id="ceed1-161">No utilice los tipos como objetos de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ceed1-161">Don't use types as lock objects.</span></span> <span data-ttu-id="ceed1-162">Es decir, evite código como `lock(typeof(X))` en C# o `SyncLock(GetType(X))` en Visual Basic o el uso de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> con objetos <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ceed1-162">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="ceed1-163">Para un tipo determinado, hay sólo una instancia de <xref:System.Type?displayProperty=nameWithType> por el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ceed1-163">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="ceed1-164">Si el tipo que quiere bloquear es público, codifique uno que su tipo no pueda bloquear, para evitar interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-164">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="ceed1-165">Para otros problemas, consulte [Procedimientos recomendados para la confiabilidad](../../../docs/framework/performance/reliability-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="ceed1-165">For additional issues, see [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md).</span></span>  
  
-   <span data-ttu-id="ceed1-166">Tenga cuidado al efectuar bloqueos en instancias, por ejemplo `lock(this)` en C# o `SyncLock(Me)` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ceed1-166">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="ceed1-167">Si otra parte del código de la aplicación, ajeno al tipo, bloquea el objeto, podrían producirse interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-167">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
-   <span data-ttu-id="ceed1-168">Asegúrese de que un subproceso que entra en un monitor siempre sale de ese monitor, aun en el caso de que se produzca una excepción mientras el subproceso se encuentra en el monitor.</span><span class="sxs-lookup"><span data-stu-id="ceed1-168">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="ceed1-169">La instrucción [lock](~/docs/csharp/language-reference/keywords/lock-statement.md) de C# y la instrucción [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md) de Visual Basic ofrecen automáticamente este comportamiento mediante un bloque **finally** que garantiza la llamada a <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ceed1-169">The C# [lock](~/docs/csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="ceed1-170">Si no está seguro de que se llamará a **Exit**, considere la posibilidad de cambiar el diseño con el fin de usar **Mutex**.</span><span class="sxs-lookup"><span data-stu-id="ceed1-170">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="ceed1-171">Una zona de exclusión mutua se libera automáticamente cuando finaliza el subproceso al que pertenece.</span><span class="sxs-lookup"><span data-stu-id="ceed1-171">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
-   <span data-ttu-id="ceed1-172">Utilice varios subprocesos para tareas que requieren recursos diferentes, y evite asignar varios subprocesos a un solo recurso.</span><span class="sxs-lookup"><span data-stu-id="ceed1-172">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="ceed1-173">Por ejemplo, en tareas que impliquen beneficios de E/S por tener un subproceso propio, ya que ese subproceso se bloquea durante las operaciones de E/S y, de este modo, permite ejecutar otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-173">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="ceed1-174">Los datos proporcionados por el usuario son otro recurso que se beneficia de la utilización de un subproceso dedicado.</span><span class="sxs-lookup"><span data-stu-id="ceed1-174">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="ceed1-175">En un equipo de un solo procesador, una tarea que implica un cálculo intensivo coexiste con los datos proporcionados por el usuario y con tareas que implican la E/S, pero varias tareas de cálculo intensivo compiten entre ellas.</span><span class="sxs-lookup"><span data-stu-id="ceed1-175">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
-   <span data-ttu-id="ceed1-176">Considere la posibilidad de utilizar métodos de la clase <xref:System.Threading.Interlocked> para los cambios de estado simples, en lugar de utilizar la instrucción `lock` (`SyncLock` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ceed1-176">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="ceed1-177">La instrucción `lock` es una buena herramienta de uso general, pero la clase <xref:System.Threading.Interlocked> genera mejor rendimiento para las actualizaciones que deben ser atómicas.</span><span class="sxs-lookup"><span data-stu-id="ceed1-177">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="ceed1-178">Internamente, ejecuta un solo prefijo de bloqueo si no hay contención.</span><span class="sxs-lookup"><span data-stu-id="ceed1-178">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="ceed1-179">En las revisiones de código, inspeccione código similar al que se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ceed1-179">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="ceed1-180">En el primer ejemplo, se incrementa una variable de estado:</span><span class="sxs-lookup"><span data-stu-id="ceed1-180">In the first example, a state variable is incremented:</span></span>  
  
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
  
     <span data-ttu-id="ceed1-181">Para mejorar el rendimiento, utilice el método <xref:System.Threading.Interlocked.Increment%2A> en lugar de la instrucción `lock`, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ceed1-181">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ceed1-182">En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.Add%2A> proporciona actualizaciones atómicas en incrementos mayores que 1.</span><span class="sxs-lookup"><span data-stu-id="ceed1-182">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Add%2A> method provides atomic updates in increments larger than 1.</span></span>  
  
     <span data-ttu-id="ceed1-183">En el segundo ejemplo, se actualiza una variable de tipo de referencia sólo si es una referencia nula (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ceed1-183">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
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
            if (x == null)  
            {  
                x = y;  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="ceed1-184">Se puede mejorar el rendimiento utilizando el método <xref:System.Threading.Interlocked.CompareExchange%2A> de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ceed1-184">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ceed1-185">En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.CompareExchange%2A> tiene una sobrecarga genérica que se puede utilizar para el reemplazo con seguridad de tipos de cualquier tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="ceed1-185">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.CompareExchange%2A> method has a generic overload that can be used for type-safe replacement of any reference type.</span></span>  
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="ceed1-186">Recomendaciones para las bibliotecas de clases</span><span class="sxs-lookup"><span data-stu-id="ceed1-186">Recommendations for Class Libraries</span></span>  
 <span data-ttu-id="ceed1-187">Tenga en cuenta las instrucciones siguientes cuando diseñe bibliotecas de clases para el multithreading:</span><span class="sxs-lookup"><span data-stu-id="ceed1-187">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
-   <span data-ttu-id="ceed1-188">Evite la necesidad de sincronización si es posible.</span><span class="sxs-lookup"><span data-stu-id="ceed1-188">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="ceed1-189">Esto se aplica especialmente en el caso de código muy utilizado.</span><span class="sxs-lookup"><span data-stu-id="ceed1-189">This is especially true for heavily used code.</span></span> <span data-ttu-id="ceed1-190">Por ejemplo, se podría ajustar un algoritmo de modo que tolere una condición de carrera en lugar de eliminarla.</span><span class="sxs-lookup"><span data-stu-id="ceed1-190">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="ceed1-191">La sincronización innecesaria disminuye el rendimiento y crea la posibilidad de interbloqueos y condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="ceed1-191">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
-   <span data-ttu-id="ceed1-192">Procure que los datos estáticos (`Shared` en Visual Basic) sean seguros para subprocesos de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ceed1-192">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
-   <span data-ttu-id="ceed1-193">No convierta los datos de instancia en datos seguros para subprocesos de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ceed1-193">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="ceed1-194">Al agregar bloqueos para crear código seguro para subprocesos, se reduce el rendimiento, se incrementa la contención de bloqueos y se crea la posibilidad de que se produzcan interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-194">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="ceed1-195">En los modelos de aplicación comunes, sólo un subproceso a la vez ejecuta código de usuario, lo que minimiza la necesidad de la seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-195">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="ceed1-196">Por esta razón, las bibliotecas de clases de .NET Framework no son seguras para subprocesos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ceed1-196">For this reason, the .NET Framework class libraries are not thread safe by default.</span></span>  
  
-   <span data-ttu-id="ceed1-197">Evite proporcionar métodos estáticos que alteren el estado estático.</span><span class="sxs-lookup"><span data-stu-id="ceed1-197">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="ceed1-198">En escenarios de servidor comunes, el estado estático se comparte entre las solicitudes, lo que significa que varios subprocesos pueden ejecutar a la vez ese código.</span><span class="sxs-lookup"><span data-stu-id="ceed1-198">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="ceed1-199">De este modo, se abre la posibilidad de errores de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ceed1-199">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="ceed1-200">Considere la posibilidad de utilizar un modelo de diseño que encapsule los datos en instancias no compartidas por las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="ceed1-200">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="ceed1-201">Además, si se sincronizan los datos estáticos, las llamadas entre los métodos estáticos que modifican el estado pueden generar interbloqueos o sincronización redundante, lo que afecta negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ceed1-201">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceed1-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceed1-202">See also</span></span>

- [<span data-ttu-id="ceed1-203">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="ceed1-203">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="ceed1-204">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="ceed1-204">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)
