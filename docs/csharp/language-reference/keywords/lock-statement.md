---
title: lock (Instrucción, Referencia de C#)
description: 'La palabra clave lock se usa en el subprocesamiento '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931198"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="101c6-103">lock (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="101c6-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="101c6-104">La palabra clave `lock` marca un bloque de instrucciones como una sección crítica. Para ello, obtiene el bloqueo de exclusión mutua para un objeto determinado, ejecuta una instrucción y, después, libera el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="101c6-104">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="101c6-105">En el ejemplo siguiente se incluye una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="101c6-105">The following example includes a `lock` statement.</span></span>

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

<span data-ttu-id="101c6-106">Para obtener más información, vea [Sincronización de subprocesos](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="101c6-106">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="101c6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="101c6-107">Remarks</span></span>

<span data-ttu-id="101c6-108">La palabra clave `lock` garantiza que un subproceso no entra en una sección crítica de código mientras otro subproceso se encuentra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="101c6-108">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="101c6-109">Si otro subproceso intenta entrar en un código bloqueado, esperará hasta que se libere el objeto.</span><span class="sxs-lookup"><span data-stu-id="101c6-109">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>

<span data-ttu-id="101c6-110">En la sección [Subprocesamiento](../../programming-guide/concepts/threading/index.md) se describen los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="101c6-110">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>

<span data-ttu-id="101c6-111">La palabra clave `lock` llama a <xref:System.Threading.Monitor.Enter%2A> al comienzo del bloque y a <xref:System.Threading.Monitor.Exit%2A> al final de este.</span><span class="sxs-lookup"><span data-stu-id="101c6-111">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="101c6-112">Se genera <xref:System.Threading.ThreadInterruptedException> si <xref:System.Threading.Thread.Interrupt%2A> interrumpe un subproceso que está esperando para especificar una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="101c6-112">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>

<span data-ttu-id="101c6-113">En general, evite el bloqueo en un tipo `public` o en instancias que estén fuera del control de su código.</span><span class="sxs-lookup"><span data-stu-id="101c6-113">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="101c6-114">Las construcciones comunes `lock (this)`, `lock (typeof (MyType))` y `lock ("myLock")` incumplen esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="101c6-114">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>

- <span data-ttu-id="101c6-115">`lock (this)` es un problema si la instancia es accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="101c6-115">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>

- <span data-ttu-id="101c6-116">`lock (typeof (MyType))` es un problema si `MyType` es accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="101c6-116">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>

- <span data-ttu-id="101c6-117">`lock("myLock")` es un problema porque cualquier otro código del proceso que use la misma cadena compartirá el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="101c6-117">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>

<span data-ttu-id="101c6-118">Se recomienda definir un objeto `private` para bloquear, o una variable de objeto `private static` para proteger los datos comunes a todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="101c6-118">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>

<span data-ttu-id="101c6-119">No se puede usar la palabra clave [await](await.md) en el cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="101c6-119">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="example---threads-without-locking"></a><span data-ttu-id="101c6-120">Ejemplo: subprocesos sin bloquear</span><span class="sxs-lookup"><span data-stu-id="101c6-120">Example - Threads without locking</span></span>

<span data-ttu-id="101c6-121">En el ejemplo siguiente se muestra un uso simple de los subprocesos sin bloquear en C#:</span><span class="sxs-lookup"><span data-stu-id="101c6-121">The following sample shows a simple use of threads without locking in C#:</span></span>

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a><span data-ttu-id="101c6-122">Ejemplo: subprocesos con bloqueo</span><span class="sxs-lookup"><span data-stu-id="101c6-122">Example - Threads using locking</span></span>

<span data-ttu-id="101c6-123">En el ejemplo siguiente se usan subprocesos y `lock`.</span><span class="sxs-lookup"><span data-stu-id="101c6-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="101c6-124">Siempre que la instrucción `lock` esté presente, el bloque de instrucciones será una sección crítica y `balance` nunca se convertirá en un número negativo:</span><span class="sxs-lookup"><span data-stu-id="101c6-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number:</span></span>

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="101c6-125">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="101c6-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="101c6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="101c6-126">See also</span></span>

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [<span data-ttu-id="101c6-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="101c6-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="101c6-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="101c6-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="101c6-129">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="101c6-129">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
- [<span data-ttu-id="101c6-130">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="101c6-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="101c6-131">Palabras clave de instrucciones</span><span class="sxs-lookup"><span data-stu-id="101c6-131">Statement Keywords</span></span>](statement-keywords.md)
- <span data-ttu-id="101c6-132">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) (Operaciones Interlocked)</span><span class="sxs-lookup"><span data-stu-id="101c6-132">[Interlocked Operations](../../../standard/threading/interlocked-operations.md)</span></span>
- [<span data-ttu-id="101c6-133">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="101c6-133">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)
- [<span data-ttu-id="101c6-134">Sincronización de subprocesos</span><span class="sxs-lookup"><span data-stu-id="101c6-134">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)