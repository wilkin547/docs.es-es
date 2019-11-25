---
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
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352816"
---
# <a name="synclock-statement"></a><span data-ttu-id="41aab-102">SyncLock (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="41aab-102">SyncLock Statement</span></span>
<span data-ttu-id="41aab-103">Acquires an exclusive lock for a statement block before executing the block.</span><span class="sxs-lookup"><span data-stu-id="41aab-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41aab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41aab-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="41aab-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="41aab-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="41aab-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="41aab-106">Required.</span></span> <span data-ttu-id="41aab-107">Expression that evaluates to an object reference.</span><span class="sxs-lookup"><span data-stu-id="41aab-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="41aab-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="41aab-108">Optional.</span></span> <span data-ttu-id="41aab-109">Block of statements that are to execute when the lock is acquired.</span><span class="sxs-lookup"><span data-stu-id="41aab-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="41aab-110">Terminates a `SyncLock` block.</span><span class="sxs-lookup"><span data-stu-id="41aab-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41aab-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41aab-111">Remarks</span></span>  
 <span data-ttu-id="41aab-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span><span class="sxs-lookup"><span data-stu-id="41aab-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="41aab-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span><span class="sxs-lookup"><span data-stu-id="41aab-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="41aab-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span><span class="sxs-lookup"><span data-stu-id="41aab-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="41aab-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span><span class="sxs-lookup"><span data-stu-id="41aab-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="41aab-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span><span class="sxs-lookup"><span data-stu-id="41aab-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="41aab-117">Reglas</span><span class="sxs-lookup"><span data-stu-id="41aab-117">Rules</span></span>  
  
- <span data-ttu-id="41aab-118">Branching.</span><span class="sxs-lookup"><span data-stu-id="41aab-118">Branching.</span></span> <span data-ttu-id="41aab-119">You cannot branch into a `SyncLock` block from outside the block.</span><span class="sxs-lookup"><span data-stu-id="41aab-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="41aab-120">Lock Object Value.</span><span class="sxs-lookup"><span data-stu-id="41aab-120">Lock Object Value.</span></span> <span data-ttu-id="41aab-121">The value of `lockobject` cannot be `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="41aab-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="41aab-122">You must create the lock object before you use it in a `SyncLock` statement.</span><span class="sxs-lookup"><span data-stu-id="41aab-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="41aab-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span><span class="sxs-lookup"><span data-stu-id="41aab-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="41aab-124">The mechanism requires that the lock object remain unchanged.</span><span class="sxs-lookup"><span data-stu-id="41aab-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="41aab-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span><span class="sxs-lookup"><span data-stu-id="41aab-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="41aab-126">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="41aab-126">Behavior</span></span>  
  
- <span data-ttu-id="41aab-127">Mechanism.</span><span class="sxs-lookup"><span data-stu-id="41aab-127">Mechanism.</span></span> <span data-ttu-id="41aab-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span><span class="sxs-lookup"><span data-stu-id="41aab-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="41aab-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span><span class="sxs-lookup"><span data-stu-id="41aab-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="41aab-130">Protected Data.</span><span class="sxs-lookup"><span data-stu-id="41aab-130">Protected Data.</span></span> <span data-ttu-id="41aab-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span><span class="sxs-lookup"><span data-stu-id="41aab-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="41aab-132">This protects data that is shared among all the instances.</span><span class="sxs-lookup"><span data-stu-id="41aab-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="41aab-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span><span class="sxs-lookup"><span data-stu-id="41aab-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="41aab-134">This protects data maintained by the individual instance.</span><span class="sxs-lookup"><span data-stu-id="41aab-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="41aab-135">Acquisition and Release.</span><span class="sxs-lookup"><span data-stu-id="41aab-135">Acquisition and Release.</span></span> <span data-ttu-id="41aab-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span><span class="sxs-lookup"><span data-stu-id="41aab-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="41aab-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span><span class="sxs-lookup"><span data-stu-id="41aab-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="41aab-138">This is true even in the case of an unhandled exception.</span><span class="sxs-lookup"><span data-stu-id="41aab-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="41aab-139">Framework Calls.</span><span class="sxs-lookup"><span data-stu-id="41aab-139">Framework Calls.</span></span> <span data-ttu-id="41aab-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span><span class="sxs-lookup"><span data-stu-id="41aab-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="41aab-141">Programming Practices</span><span class="sxs-lookup"><span data-stu-id="41aab-141">Programming Practices</span></span>  
 <span data-ttu-id="41aab-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span><span class="sxs-lookup"><span data-stu-id="41aab-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="41aab-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span><span class="sxs-lookup"><span data-stu-id="41aab-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="41aab-144">You should not use the `Me` keyword to provide a lock object for instance data.</span><span class="sxs-lookup"><span data-stu-id="41aab-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="41aab-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span><span class="sxs-lookup"><span data-stu-id="41aab-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="41aab-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span><span class="sxs-lookup"><span data-stu-id="41aab-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="41aab-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span><span class="sxs-lookup"><span data-stu-id="41aab-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="41aab-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span><span class="sxs-lookup"><span data-stu-id="41aab-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="41aab-149">This is because `GetType` always returns the same `Type` object for a given class name.</span><span class="sxs-lookup"><span data-stu-id="41aab-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="41aab-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span><span class="sxs-lookup"><span data-stu-id="41aab-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="41aab-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span><span class="sxs-lookup"><span data-stu-id="41aab-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="41aab-152">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="41aab-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="41aab-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="41aab-153">Description</span></span>  
 <span data-ttu-id="41aab-154">The following example shows a class that maintains a simple list of messages.</span><span class="sxs-lookup"><span data-stu-id="41aab-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="41aab-155">It holds the messages in an array and the last used element of that array in a variable.</span><span class="sxs-lookup"><span data-stu-id="41aab-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="41aab-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span><span class="sxs-lookup"><span data-stu-id="41aab-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="41aab-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span><span class="sxs-lookup"><span data-stu-id="41aab-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="41aab-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span><span class="sxs-lookup"><span data-stu-id="41aab-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="41aab-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span><span class="sxs-lookup"><span data-stu-id="41aab-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41aab-160">Código</span><span class="sxs-lookup"><span data-stu-id="41aab-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="41aab-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="41aab-161">Description</span></span>  
 <span data-ttu-id="41aab-162">The following example uses threads and `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="41aab-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="41aab-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span><span class="sxs-lookup"><span data-stu-id="41aab-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="41aab-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span><span class="sxs-lookup"><span data-stu-id="41aab-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41aab-165">Código</span><span class="sxs-lookup"><span data-stu-id="41aab-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="41aab-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41aab-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41aab-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="41aab-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="41aab-168">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="41aab-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
