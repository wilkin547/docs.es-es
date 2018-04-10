---
title: lock (Instrucción, Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb48c2b1554ad2817406eaef42b4cb336ea46862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="e08c5-102">lock (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e08c5-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="e08c5-103">La palabra clave `lock` marca un bloque de instrucciones como una sección crítica. Para ello, obtiene el bloqueo de exclusión mutua para un objeto determinado, ejecuta una instrucción y, después, libera el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e08c5-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="e08c5-104">En el ejemplo siguiente se incluye una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="e08c5-104">The following example includes a `lock` statement.</span></span>  
  
```csharp  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e08c5-105">Para obtener más información, vea [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e08c5-105">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e08c5-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e08c5-106">Remarks</span></span>  
 <span data-ttu-id="e08c5-107">La palabra clave `lock` garantiza que un subproceso no entra en una sección crítica de código mientras otro subproceso se encuentra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="e08c5-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="e08c5-108">Si otro subproceso intenta entrar en un código bloqueado, esperará hasta que se libere el objeto.</span><span class="sxs-lookup"><span data-stu-id="e08c5-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="e08c5-109">En la sección [Subprocesamiento](../../programming-guide/concepts/threading/index.md) se describen los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e08c5-109">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>  
  
 <span data-ttu-id="e08c5-110">La palabra clave `lock` llama a <xref:System.Threading.Monitor.Enter%2A> al comienzo del bloque y a <xref:System.Threading.Monitor.Exit%2A> al final de este.</span><span class="sxs-lookup"><span data-stu-id="e08c5-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="e08c5-111">Se genera <xref:System.Threading.ThreadInterruptedException> si <xref:System.Threading.Thread.Interrupt%2A> interrumpe un subproceso que está esperando para especificar una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="e08c5-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="e08c5-112">En general, evite el bloqueo en un tipo `public` o en instancias que estén fuera del control de su código.</span><span class="sxs-lookup"><span data-stu-id="e08c5-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="e08c5-113">Las construcciones comunes `lock (this)`, `lock (typeof (MyType))` y `lock ("myLock")` incumplen esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="e08c5-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="e08c5-114">`lock (this)` es un problema si la instancia es accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="e08c5-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="e08c5-115">`lock (typeof (MyType))` es un problema si `MyType` es accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="e08c5-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="e08c5-116">`lock("myLock")` es un problema porque cualquier otro código del proceso que use la misma cadena compartirá el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e08c5-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="e08c5-117">Se recomienda definir un objeto `private` para bloquear, o una variable de objeto `private static` para proteger los datos comunes a todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="e08c5-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="e08c5-118">No se puede usar la palabra clave [await](../../../csharp/language-reference/keywords/await.md) en el cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="e08c5-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08c5-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e08c5-119">Example</span></span>  
 <span data-ttu-id="e08c5-120">En el ejemplo siguiente se muestra un uso simple de subprocesos sin bloquear en C#.</span><span class="sxs-lookup"><span data-stu-id="e08c5-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e08c5-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e08c5-121">Example</span></span>  
 <span data-ttu-id="e08c5-122">En el ejemplo siguiente se usan subprocesos y `lock`.</span><span class="sxs-lookup"><span data-stu-id="e08c5-122">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="e08c5-123">Siempre que la instrucción `lock` esté presente, el bloque de instrucciones será una sección crítica y `balance` nunca se convertirá en un número negativo.</span><span class="sxs-lookup"><span data-stu-id="e08c5-123">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e08c5-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e08c5-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e08c5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e08c5-125">See Also</span></span>  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [<span data-ttu-id="e08c5-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e08c5-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e08c5-127">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e08c5-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e08c5-128">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="e08c5-128">Threading</span></span>](../../programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="e08c5-129">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="e08c5-129">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e08c5-130">Palabras clave de instrucciones</span><span class="sxs-lookup"><span data-stu-id="e08c5-130">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 <span data-ttu-id="e08c5-131">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) (Operaciones Interlocked)</span><span class="sxs-lookup"><span data-stu-id="e08c5-131">[Interlocked Operations](../../../standard/threading/interlocked-operations.md)</span></span>  
 [<span data-ttu-id="e08c5-132">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="e08c5-132">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="e08c5-133">Sincronización de subprocesos</span><span class="sxs-lookup"><span data-stu-id="e08c5-133">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)
