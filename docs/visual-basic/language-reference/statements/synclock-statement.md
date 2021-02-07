---
description: 'Más información acerca de: SyncLock (instrucción)'
title: SyncLock (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 206c10c8bca85a496345576d0d5f9ff260db82e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740982"
---
# <a name="synclock-statement"></a><span data-ttu-id="88288-103">SyncLock (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="88288-103">SyncLock Statement</span></span>

<span data-ttu-id="88288-104">Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-104">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88288-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88288-105">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="88288-106">Partes</span><span class="sxs-lookup"><span data-stu-id="88288-106">Parts</span></span>  

 `lockobject`  
 <span data-ttu-id="88288-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="88288-107">Required.</span></span> <span data-ttu-id="88288-108">Expresión que se evalúa como una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="88288-108">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="88288-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="88288-109">Optional.</span></span> <span data-ttu-id="88288-110">Bloque de instrucciones que se ejecutan cuando se adquiere el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="88288-110">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="88288-111">Finaliza un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-111">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88288-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88288-112">Remarks</span></span>  

 <span data-ttu-id="88288-113">La `SyncLock` instrucción garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="88288-113">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="88288-114">`SyncLock` impide que cada subproceso entre en el bloque hasta que no lo ejecute ningún otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="88288-114">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="88288-115">El uso más común de `SyncLock` es proteger los datos de la actualización por parte de más de un subproceso simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="88288-115">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="88288-116">Si las instrucciones que manipulan los datos deben ir a la finalización sin interrupción, colóquelos dentro de un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-116">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="88288-117">Un bloque de instrucciones protegido por un bloqueo exclusivo a veces se denomina *sección crítica*.</span><span class="sxs-lookup"><span data-stu-id="88288-117">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="88288-118">Reglas</span><span class="sxs-lookup"><span data-stu-id="88288-118">Rules</span></span>  
  
- <span data-ttu-id="88288-119">Bifurcación.</span><span class="sxs-lookup"><span data-stu-id="88288-119">Branching.</span></span> <span data-ttu-id="88288-120">No se puede crear una bifurcación en un `SyncLock` bloque desde fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-120">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="88288-121">Valor de bloqueo de objeto.</span><span class="sxs-lookup"><span data-stu-id="88288-121">Lock Object Value.</span></span> <span data-ttu-id="88288-122">El valor de `lockobject` no puede ser `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="88288-122">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="88288-123">Debe crear el objeto de bloqueo antes de usarlo en una `SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="88288-123">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="88288-124">No se puede cambiar el valor de `lockobject` mientras se ejecuta un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-124">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="88288-125">El mecanismo requiere que el objeto de bloqueo permanezca sin cambios.</span><span class="sxs-lookup"><span data-stu-id="88288-125">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="88288-126">No se puede usar el operador [Await](../operators/await-operator.md) en un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-126">You can't use the [Await](../operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="88288-127">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="88288-127">Behavior</span></span>  
  
- <span data-ttu-id="88288-128">Método.</span><span class="sxs-lookup"><span data-stu-id="88288-128">Mechanism.</span></span> <span data-ttu-id="88288-129">Cuando un subproceso alcanza la `SyncLock` instrucción, evalúa la `lockobject` expresión y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión.</span><span class="sxs-lookup"><span data-stu-id="88288-129">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="88288-130">Cuando otro subproceso alcanza la `SyncLock` instrucción, no adquiere un bloqueo hasta que el primer subproceso ejecuta la `End SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="88288-130">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="88288-131">Datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="88288-131">Protected Data.</span></span> <span data-ttu-id="88288-132">Si `lockobject` es una `Shared` variable, el bloqueo exclusivo impide que un subproceso de una instancia de la clase ejecute el `SyncLock` bloque mientras otro subproceso lo está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="88288-132">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="88288-133">Esto protege los datos que se comparten entre todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="88288-133">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="88288-134">Si `lockobject` es una variable de instancia (no `Shared` ), el bloqueo impide que un subproceso que se ejecuta en la instancia actual ejecute el `SyncLock` bloque al mismo tiempo que otro subproceso de la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="88288-134">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="88288-135">Esto protege los datos mantenidos por la instancia individual.</span><span class="sxs-lookup"><span data-stu-id="88288-135">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="88288-136">Adquisición y lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="88288-136">Acquisition and Release.</span></span> <span data-ttu-id="88288-137">Un `SyncLock` bloque se comporta como una `Try...Finally` construcción en la que el `Try` bloque adquiere un bloqueo exclusivo en `lockobject` y el `Finally` bloque lo libera.</span><span class="sxs-lookup"><span data-stu-id="88288-137">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="88288-138">Por este motivo, el `SyncLock` bloque garantiza la liberación del bloqueo, independientemente de cómo salga del bloque.</span><span class="sxs-lookup"><span data-stu-id="88288-138">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="88288-139">Esto es así incluso en el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="88288-139">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="88288-140">Llamadas de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="88288-140">Framework Calls.</span></span> <span data-ttu-id="88288-141">El `SyncLock` bloque adquiere y libera el bloqueo exclusivo mediante una llamada a `Enter` los `Exit` métodos y de la `Monitor` clase en el <xref:System.Threading> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="88288-141">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="88288-142">Prácticas de programación</span><span class="sxs-lookup"><span data-stu-id="88288-142">Programming Practices</span></span>  

 <span data-ttu-id="88288-143">La `lockobject` expresión siempre debe evaluarse como un objeto que pertenece exclusivamente a la clase.</span><span class="sxs-lookup"><span data-stu-id="88288-143">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="88288-144">Debe declarar una `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual o una `Private Shared` variable de objeto para proteger los datos comunes a todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="88288-144">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="88288-145">No debe utilizar la `Me` palabra clave para proporcionar un objeto de bloqueo para los datos de instancia.</span><span class="sxs-lookup"><span data-stu-id="88288-145">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="88288-146">Si el código externo a la clase tiene una referencia a una instancia de la clase, podría usar esa referencia como un objeto de bloqueo para un `SyncLock` bloque completamente diferente del suyo, protegiendo datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="88288-146">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="88288-147">De esta manera, la clase y la otra clase podrían bloquearse entre sí desde la ejecución de los `SyncLock` bloques no relacionados.</span><span class="sxs-lookup"><span data-stu-id="88288-147">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="88288-148">Un bloqueo similar en una cadena puede ser problemático, ya que cualquier otro código del proceso que use la misma cadena compartirá el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="88288-148">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="88288-149">Tampoco debe utilizar el `Me.GetType` método para proporcionar un objeto de bloqueo para los datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="88288-149">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="88288-150">Esto se debe `GetType` a que siempre devuelve el mismo `Type` objeto para un nombre de clase determinado.</span><span class="sxs-lookup"><span data-stu-id="88288-150">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="88288-151">El código externo podría llamar a `GetType` en su clase y obtener el mismo objeto de bloqueo que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="88288-151">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="88288-152">Esto daría lugar a que las dos clases se bloqueen entre sí desde sus `SyncLock` bloques.</span><span class="sxs-lookup"><span data-stu-id="88288-152">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="88288-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="88288-153">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="88288-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="88288-154">Description</span></span>  

 <span data-ttu-id="88288-155">En el ejemplo siguiente se muestra una clase que mantiene una lista de mensajes simple.</span><span class="sxs-lookup"><span data-stu-id="88288-155">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="88288-156">Contiene los mensajes de una matriz y el último elemento utilizado de esa matriz en una variable.</span><span class="sxs-lookup"><span data-stu-id="88288-156">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="88288-157">El `addAnotherMessage` procedimiento incrementa el último elemento y almacena el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="88288-157">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="88288-158">Estas dos operaciones están protegidas por las `SyncLock` `End SyncLock` instrucciones y, porque una vez que se ha incrementado el último elemento, el nuevo mensaje se debe almacenar antes de que cualquier otro subproceso pueda incrementar el último elemento de nuevo.</span><span class="sxs-lookup"><span data-stu-id="88288-158">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="88288-159">Si la `simpleMessageList` clase compartía una lista de mensajes entre todas sus instancias, las variables `messagesList` y `messagesLast` se declararían como `Shared` .</span><span class="sxs-lookup"><span data-stu-id="88288-159">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="88288-160">En este caso, la variable `messagesLock` también debe ser `Shared` , de modo que haya un solo objeto de bloqueo utilizado por cada instancia.</span><span class="sxs-lookup"><span data-stu-id="88288-160">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88288-161">Código</span><span class="sxs-lookup"><span data-stu-id="88288-161">Code</span></span>  

 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="88288-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="88288-162">Description</span></span>  

 <span data-ttu-id="88288-163">En el ejemplo siguiente se usan los subprocesos y `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="88288-163">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="88288-164">Siempre y cuando la `SyncLock` instrucción esté presente, el bloque de instrucciones es una sección crítica y `balance` nunca se convierte en un número negativo.</span><span class="sxs-lookup"><span data-stu-id="88288-164">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="88288-165">Puede comentar las `SyncLock` `End SyncLock` instrucciones y para ver el efecto de salir de la `SyncLock` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="88288-165">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88288-166">Código</span><span class="sxs-lookup"><span data-stu-id="88288-166">Code</span></span>  

 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="88288-167">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88288-167">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88288-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="88288-168">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="88288-169">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="88288-169">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
