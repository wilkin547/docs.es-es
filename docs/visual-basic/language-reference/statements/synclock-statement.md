---
title: "SyncLock (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c826e1ba592dfc4f2899a26102466d2e7df54f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="synclock-statement"></a><span data-ttu-id="be022-102">SyncLock (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="be022-102">SyncLock Statement</span></span>
<span data-ttu-id="be022-103">Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be022-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be022-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="be022-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="be022-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="be022-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="be022-106">Required.</span></span> <span data-ttu-id="be022-107">Expresión que se evalúa como una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="be022-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="be022-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be022-108">Optional.</span></span> <span data-ttu-id="be022-109">Bloque de instrucciones que se ejecuta cuando se adquiere el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="be022-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="be022-110">Finaliza un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be022-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be022-111">Remarks</span></span>  
 <span data-ttu-id="be022-112">El `SyncLock` instrucción garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="be022-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="be022-113">`SyncLock`impide que cada subproceso entra en el bloque hasta que ningún otro subproceso está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="be022-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="be022-114">El uso más común de `SyncLock` es para impedir que los datos que se va a actualizar más de un subproceso al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="be022-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="be022-115">Si las instrucciones que manipulan los datos deben ir hasta su finalización sin interrupción, colóquelos en un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="be022-116">Un bloque de instrucciones protegido por un bloqueo exclusivo se denomina a veces un *sección crítica*.</span><span class="sxs-lookup"><span data-stu-id="be022-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="be022-117">Reglas</span><span class="sxs-lookup"><span data-stu-id="be022-117">Rules</span></span>  
  
-   <span data-ttu-id="be022-118">La bifurcación.</span><span class="sxs-lookup"><span data-stu-id="be022-118">Branching.</span></span> <span data-ttu-id="be022-119">No se puede bifurcar en un `SyncLock` bloquear desde fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="be022-120">Valor de objeto de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="be022-120">Lock Object Value.</span></span> <span data-ttu-id="be022-121">El valor de `lockobject` no puede ser `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="be022-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="be022-122">Debe crear el objeto de bloqueo antes de usarlo en un `SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be022-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="be022-123">No se puede cambiar el valor de `lockobject` mientras se ejecuta un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="be022-124">El mecanismo requiere que el objeto de bloqueo permanezca sin cambios.</span><span class="sxs-lookup"><span data-stu-id="be022-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="be022-125">No se puede utilizar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="be022-126">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="be022-126">Behavior</span></span>  
  
-   <span data-ttu-id="be022-127">Mecanismo.</span><span class="sxs-lookup"><span data-stu-id="be022-127">Mechanism.</span></span> <span data-ttu-id="be022-128">Cuando un subproceso llegue el `SyncLock` instrucción, se evalúa como el `lockobject` expresión y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión.</span><span class="sxs-lookup"><span data-stu-id="be022-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="be022-129">Cuando otro subproceso llegue el `SyncLock` (instrucción), no podrá adquirir un bloqueo hasta que el primer subproceso se ejecuta el `End SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be022-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="be022-130">Los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="be022-130">Protected Data.</span></span> <span data-ttu-id="be022-131">Si `lockobject` es un `Shared` variable, el bloqueo exclusivo impide que un subproceso en cualquier instancia de la clase de ejecutar el `SyncLock` bloquear mientras está ejecutando ningún otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="be022-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="be022-132">Esto protege los datos que se comparten entre todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="be022-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="be022-133">Si `lockobject` es una variable de instancia (no `Shared`), el bloqueo impide que un subproceso que se ejecuta en la instancia actual de ejecutarse el `SyncLock` se bloqueen en el mismo tiempo que otro subproceso en la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="be022-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="be022-134">Esto protege los datos mantenidos por la instancia individual.</span><span class="sxs-lookup"><span data-stu-id="be022-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="be022-135">Adquisición y liberación.</span><span class="sxs-lookup"><span data-stu-id="be022-135">Acquisition and Release.</span></span> <span data-ttu-id="be022-136">A `SyncLock` bloque se comporta como un `Try...Finally` construcción en el que el `Try` bloque adquiere un bloqueo exclusivo en `lockobject` y `Finally` bloqueo lo libere.</span><span class="sxs-lookup"><span data-stu-id="be022-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="be022-137">Por este motivo, la `SyncLock` bloque garantiza la liberación del bloqueo, independientemente de cómo salga del bloque.</span><span class="sxs-lookup"><span data-stu-id="be022-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="be022-138">Esto es cierto incluso si se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="be022-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="be022-139">Llamadas de Framework.</span><span class="sxs-lookup"><span data-stu-id="be022-139">Framework Calls.</span></span> <span data-ttu-id="be022-140">El `SyncLock` bloque adquiere y libera el bloqueo exclusivo mediante una llamada a la `Enter` y `Exit` métodos de la `Monitor` clase en el <xref:System.Threading> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="be022-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="be022-141">Prácticas recomendadas de programación</span><span class="sxs-lookup"><span data-stu-id="be022-141">Programming Practices</span></span>  
 <span data-ttu-id="be022-142">El `lockobject` expresión siempre se debe evaluar como un objeto que pertenece exclusivamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="be022-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="be022-143">Solo debe declararse un `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual, o un `Private Shared` variable de objeto para proteger los datos comunes a todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="be022-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="be022-144">No debe utilizar el `Me` datos de palabra clave que se va a proporcionar un bloqueo de objetos para la instancia.</span><span class="sxs-lookup"><span data-stu-id="be022-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="be022-145">Si el código externo a la clase tiene una referencia a una instancia de la clase, podría utilizar esa referencia como un objeto de bloqueo para un `SyncLock` bloque completamente distinto del suyo y proteger datos distintos.</span><span class="sxs-lookup"><span data-stu-id="be022-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="be022-146">De este modo, la clase y la otra clase podrían se bloquean entre sí de ejecutar sus no relacionados `SyncLock` bloques.</span><span class="sxs-lookup"><span data-stu-id="be022-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="be022-147">De forma similar un bloqueo en una cadena puede ser problemático, ya que cualquier otro código en el proceso con la misma cadena compartirán el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="be022-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="be022-148">No debe utilizar el `Me.GetType` método para proporcionar un objeto de bloqueo de los datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="be022-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="be022-149">Esto es porque `GetType` siempre devuelve el mismo `Type` objeto para un nombre de clase determinado.</span><span class="sxs-lookup"><span data-stu-id="be022-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="be022-150">Podría llamar código externo `GetType` en su clase y obtener el mismo objeto de bloqueo que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="be022-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="be022-151">Eso resultaría en las dos clases de bloqueo entre sí de sus `SyncLock` bloques.</span><span class="sxs-lookup"><span data-stu-id="be022-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="be022-152">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="be022-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="be022-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="be022-153">Description</span></span>  
 <span data-ttu-id="be022-154">En el ejemplo siguiente se muestra una clase que mantiene una lista simple de mensajes.</span><span class="sxs-lookup"><span data-stu-id="be022-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="be022-155">Contiene los mensajes de una matriz y el último elemento utilizado de esa matriz en una variable.</span><span class="sxs-lookup"><span data-stu-id="be022-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="be022-156">El `addAnotherMessage` procedimiento aumenta el valor del último elemento y almacena el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="be022-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="be022-157">Esas dos operaciones están protegidas por el `SyncLock` y `End SyncLock` instrucciones, porque una vez que se ha incrementado el último elemento, se debe almacenar el nuevo mensaje antes de que ningún otro subproceso puede incrementar el último elemento nuevo.</span><span class="sxs-lookup"><span data-stu-id="be022-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="be022-158">Si el `simpleMessageList` clase compartiera una lista de mensajes entre todas las instancias, las variables `messagesList` y `messagesLast` se declararía como `Shared`.</span><span class="sxs-lookup"><span data-stu-id="be022-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="be022-159">En este caso, la variable `messagesLock` también debe ser `Shared`, por lo que sería un único objeto de bloqueo utilizado por todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="be022-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="be022-160">Código</span><span class="sxs-lookup"><span data-stu-id="be022-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="be022-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="be022-161">Description</span></span>  
 <span data-ttu-id="be022-162">En el siguiente ejemplo utiliza subprocesos y `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="be022-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="be022-163">Siempre y cuando la `SyncLock` instrucción está presente, el bloque de instrucciones constituye una sección crítica y `balance` nunca se convierte en un número negativo.</span><span class="sxs-lookup"><span data-stu-id="be022-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="be022-164">Puede convertir en comentario la `SyncLock` y `End SyncLock` instrucciones para ver el efecto de dejar la `SyncLock` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="be022-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="be022-165">Código</span><span class="sxs-lookup"><span data-stu-id="be022-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="be022-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be022-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be022-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="be022-167">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="be022-168">Sincronización de subprocesos</span><span class="sxs-lookup"><span data-stu-id="be022-168">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)  
 [<span data-ttu-id="be022-169">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="be022-169">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)
