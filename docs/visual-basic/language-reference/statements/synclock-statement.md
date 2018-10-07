---
title: SyncLock (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 5a931199ff8d09412d536a173f3cd12e451def64
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48845985"
---
# <a name="synclock-statement"></a><span data-ttu-id="437d5-102">SyncLock (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="437d5-102">SyncLock Statement</span></span>
<span data-ttu-id="437d5-103">Adquiere un bloqueo exclusivo para un bloque de instrucciones antes de ejecutar el bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="437d5-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="437d5-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="437d5-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="437d5-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="437d5-106">Required.</span></span> <span data-ttu-id="437d5-107">Expresión que se evalúa como una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="437d5-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="437d5-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="437d5-108">Optional.</span></span> <span data-ttu-id="437d5-109">Bloque de instrucciones que se ejecuta cuando se adquiere el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="437d5-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="437d5-110">Finaliza un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="437d5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="437d5-111">Remarks</span></span>  
 <span data-ttu-id="437d5-112">El `SyncLock` instrucción garantiza que varios subprocesos no ejecuten el bloque de instrucciones al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="437d5-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="437d5-113">`SyncLock` impide que cada subproceso entra en el bloque hasta que no está ejecutando ningún otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="437d5-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="437d5-114">El uso más común de `SyncLock` consiste en proteger los datos se actualice mediante varios subprocesos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="437d5-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="437d5-115">Si las instrucciones que manipulan los datos deben ir hasta su finalización sin interrupción, colocarlos dentro un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="437d5-116">Un bloque de instrucciones protegido por un bloqueo exclusivo a veces se denomina un *sección crítica*.</span><span class="sxs-lookup"><span data-stu-id="437d5-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="437d5-117">Reglas</span><span class="sxs-lookup"><span data-stu-id="437d5-117">Rules</span></span>  
  
-   <span data-ttu-id="437d5-118">La bifurcación.</span><span class="sxs-lookup"><span data-stu-id="437d5-118">Branching.</span></span> <span data-ttu-id="437d5-119">No puede bifurcarse en un `SyncLock` bloquear desde fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="437d5-120">Valor de objeto de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="437d5-120">Lock Object Value.</span></span> <span data-ttu-id="437d5-121">El valor de `lockobject` no puede ser `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="437d5-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="437d5-122">Debe crear el objeto de bloqueo antes de usarlo en un `SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="437d5-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="437d5-123">No se puede cambiar el valor de `lockobject` mientras se ejecuta un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="437d5-124">El mecanismo requiere que el objeto de bloqueo permanecen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="437d5-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="437d5-125">No puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en un `SyncLock` bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="437d5-126">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="437d5-126">Behavior</span></span>  
  
-   <span data-ttu-id="437d5-127">Mecanismo.</span><span class="sxs-lookup"><span data-stu-id="437d5-127">Mechanism.</span></span> <span data-ttu-id="437d5-128">Cuando un subproceso llega la `SyncLock` instrucción, se evalúa como el `lockobject` expresión y suspende la ejecución hasta que adquiere un bloqueo exclusivo en el objeto devuelto por la expresión.</span><span class="sxs-lookup"><span data-stu-id="437d5-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="437d5-129">Cuando se alcance otro subproceso el `SyncLock` instrucción, no podrá adquirir un bloqueo hasta que se ejecuta el primer subproceso el `End SyncLock` instrucción.</span><span class="sxs-lookup"><span data-stu-id="437d5-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="437d5-130">Datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="437d5-130">Protected Data.</span></span> <span data-ttu-id="437d5-131">Si `lockobject` es un `Shared` variable, el bloqueo exclusivo impide que un subproceso en cualquier instancia de la clase ejecutando el `SyncLock` bloquear mientras está ejecutando ningún otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="437d5-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="437d5-132">Esto protege los datos que se comparten entre todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="437d5-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="437d5-133">Si `lockobject` es una variable de instancia (no `Shared`), el bloqueo impide que un subproceso que se ejecuta en la instancia actual de ejecutar el `SyncLock` bloque al mismo tiempo que otro subproceso en la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="437d5-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="437d5-134">Esto protege los datos mantenidos por la instancia individual.</span><span class="sxs-lookup"><span data-stu-id="437d5-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="437d5-135">Adquisición y liberación.</span><span class="sxs-lookup"><span data-stu-id="437d5-135">Acquisition and Release.</span></span> <span data-ttu-id="437d5-136">Un `SyncLock` bloque se comporta como un `Try...Finally` construcción en el que el `Try` bloque adquiere un bloqueo exclusivo en `lockobject` y `Finally` bloqueo lo libere.</span><span class="sxs-lookup"><span data-stu-id="437d5-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="437d5-137">Por este motivo, la `SyncLock` bloque garantiza la liberación del bloqueo, independientemente de cómo salga el bloque.</span><span class="sxs-lookup"><span data-stu-id="437d5-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="437d5-138">Esto es cierto incluso si se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="437d5-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="437d5-139">Llamadas de Framework.</span><span class="sxs-lookup"><span data-stu-id="437d5-139">Framework Calls.</span></span> <span data-ttu-id="437d5-140">El `SyncLock` bloque adquiere y libera el bloqueo exclusivo mediante una llamada a la `Enter` y `Exit` métodos de la `Monitor` clase en el <xref:System.Threading> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="437d5-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="437d5-141">Prácticas recomendadas de programación</span><span class="sxs-lookup"><span data-stu-id="437d5-141">Programming Practices</span></span>  
 <span data-ttu-id="437d5-142">El `lockobject` expresión siempre debe evaluarse como un objeto que pertenece exclusivamente a la clase.</span><span class="sxs-lookup"><span data-stu-id="437d5-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="437d5-143">Se debe declarar un `Private` variable de objeto para proteger los datos que pertenecen a la instancia actual, o un `Private Shared` variable de objeto para proteger los datos comunes a todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="437d5-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="437d5-144">No se debe usar el `Me` palabra clave para proporcionar un bloqueo de objeto por ejemplo datos.</span><span class="sxs-lookup"><span data-stu-id="437d5-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="437d5-145">Si el código externo a la clase tiene una referencia a una instancia de la clase, podría usar esa referencia como un objeto de bloqueo para un `SyncLock` bloque totalmente distinto del suyo, protección de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="437d5-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="437d5-146">De este modo, la clase y la otra clase podrían se bloquean entre sí de ejecutar sus no relacionadas `SyncLock` bloques.</span><span class="sxs-lookup"><span data-stu-id="437d5-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="437d5-147">El bloqueo de forma similar en una cadena puede ser problemático, ya que cualquier otro código en el proceso con la misma cadena compartirá el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="437d5-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="437d5-148">No debe utilizar el `Me.GetType` método para proporcionar un objeto de bloqueo de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="437d5-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="437d5-149">Esto es porque `GetType` siempre devuelve el mismo `Type` objeto para un nombre de clase determinada.</span><span class="sxs-lookup"><span data-stu-id="437d5-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="437d5-150">Podría llamar código externo `GetType` en su clase y obtener el mismo objeto de bloqueo que se usa.</span><span class="sxs-lookup"><span data-stu-id="437d5-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="437d5-151">Esto daría lugar a las dos clases de bloqueo entre sí desde sus `SyncLock` bloques.</span><span class="sxs-lookup"><span data-stu-id="437d5-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="437d5-152">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="437d5-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="437d5-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="437d5-153">Description</span></span>  
 <span data-ttu-id="437d5-154">El ejemplo siguiente muestra una clase que mantiene una lista simple de mensajes.</span><span class="sxs-lookup"><span data-stu-id="437d5-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="437d5-155">Contiene los mensajes en una matriz y el último elemento de la matriz utilizado en una variable.</span><span class="sxs-lookup"><span data-stu-id="437d5-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="437d5-156">El `addAnotherMessage` procedimiento incrementa el último elemento y almacena el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="437d5-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="437d5-157">Esas dos operaciones están protegidas por la `SyncLock` y `End SyncLock` instrucciones, ya que una vez que se ha incrementado el último elemento, se debe almacenar el nuevo mensaje antes de que ningún otro subproceso puede incrementar el último elemento nuevo.</span><span class="sxs-lookup"><span data-stu-id="437d5-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="437d5-158">Si el `simpleMessageList` comparte una lista de mensajes entre todas sus instancias, las variables de clase `messagesList` y `messagesLast` se declararía como `Shared`.</span><span class="sxs-lookup"><span data-stu-id="437d5-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="437d5-159">En este caso, la variable `messagesLock` también debe ser `Shared`, de modo que sería un objeto único bloqueo utilizado por todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="437d5-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="437d5-160">Código</span><span class="sxs-lookup"><span data-stu-id="437d5-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="437d5-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="437d5-161">Description</span></span>  
 <span data-ttu-id="437d5-162">En el ejemplo siguiente se usa subprocesos y `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="437d5-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="437d5-163">Siempre y cuando la `SyncLock` instrucción está presente, el bloque de instrucciones es una sección crítica y `balance` nunca se convierte en un número negativo.</span><span class="sxs-lookup"><span data-stu-id="437d5-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="437d5-164">Puede marcar como comentario el `SyncLock` y `End SyncLock` instrucciones para ver el efecto de omitir el `SyncLock` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="437d5-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="437d5-165">Código</span><span class="sxs-lookup"><span data-stu-id="437d5-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="437d5-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="437d5-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437d5-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="437d5-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="437d5-168">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="437d5-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
