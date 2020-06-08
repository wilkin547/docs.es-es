---
title: 'Instrucción lock: Referencia de C#'
description: Use la instrucción lock de C# para sincronizar el acceso de un subproceso al recurso compartido
ms.date: 04/02/2020
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6e9a6975977588ba7692c925d7940cd2ec26671f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406695"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="65ce1-103">Instrucción lock (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="65ce1-103">lock statement (C# reference)</span></span>

<span data-ttu-id="65ce1-104">La instrucción `lock` adquiere el bloqueo de exclusión mutua de un objeto determinado, ejecuta un bloque de instrucciones y luego libera el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65ce1-104">The `lock` statement acquires the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="65ce1-105">Mientras se mantiene un bloqueo, el subproceso que lo mantiene puede volver a adquirir y liberar el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65ce1-105">While a lock is held, the thread that holds the lock can again acquire and release the lock.</span></span> <span data-ttu-id="65ce1-106">Ningún otro subproceso puede adquirir el bloqueo y espera hasta que se libera.</span><span class="sxs-lookup"><span data-stu-id="65ce1-106">Any other thread is blocked from acquiring the lock and waits until the lock is released.</span></span>

<span data-ttu-id="65ce1-107">La instrucción `lock` tiene el formato</span><span class="sxs-lookup"><span data-stu-id="65ce1-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="65ce1-108">donde `x` es una expresión de un [tipo de referencia](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="65ce1-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="65ce1-109">Es exactamente equivalente a</span><span class="sxs-lookup"><span data-stu-id="65ce1-109">It's precisely equivalent to</span></span>

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

<span data-ttu-id="65ce1-110">Puesto que el código usa un bloque [try... finally](try-finally.md), el bloqueo se libera aunque se produzca una excepción dentro del cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="65ce1-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="65ce1-111">No se puede usar el operador [await](../operators/await.md) en el cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="65ce1-111">You can't use the [await operator](../operators/await.md) in the body of a `lock` statement.</span></span>

## <a name="guidelines"></a><span data-ttu-id="65ce1-112">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="65ce1-112">Guidelines</span></span>

<span data-ttu-id="65ce1-113">Al sincronizar el acceso del subproceso al recurso compartido, bloquee una instancia dedicada de objeto (por ejemplo, `private readonly object balanceLock = new object();`) u otra instancia cuyo empleo como objeto de bloqueo sea poco probable por parte de elementos no relacionados del código.</span><span class="sxs-lookup"><span data-stu-id="65ce1-113">When you synchronize thread access to a shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="65ce1-114">Evite el uso de la misma instancia de objeto de bloqueo para distintos recursos compartidos, ya que se podría producir un interbloqueo o una contención de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65ce1-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="65ce1-115">En particular, evite utilizar lo siguiente como objetos de bloqueo:</span><span class="sxs-lookup"><span data-stu-id="65ce1-115">In particular, avoid using the following as lock objects:</span></span>

- <span data-ttu-id="65ce1-116">`this`, porque los autores de llamadas podrían usarlo como un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65ce1-116">`this`, as it might be used by the callers as a lock.</span></span>
- <span data-ttu-id="65ce1-117">Instancias <xref:System.Type>, porque el operador o la reflexión [typeof](../operators/type-testing-and-cast.md#typeof-operator) podrían obtenerlas.</span><span class="sxs-lookup"><span data-stu-id="65ce1-117"><xref:System.Type> instances, as those might be obtained by the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator or reflection.</span></span>
- <span data-ttu-id="65ce1-118">Instancias de cadena, incluidos literales de cadena, porque podrían [internarse](/dotnet/api/system.string.intern#remarks).</span><span class="sxs-lookup"><span data-stu-id="65ce1-118">string instances, including string literals, as those might be [interned](/dotnet/api/system.string.intern#remarks).</span></span>

<span data-ttu-id="65ce1-119">Mantenga el bloqueo durante el menor tiempo posible para reducir la contención de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65ce1-119">Hold a lock for as short time as possible to reduce lock contention.</span></span>

## <a name="example"></a><span data-ttu-id="65ce1-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="65ce1-120">Example</span></span>

<span data-ttu-id="65ce1-121">En el ejemplo siguiente se define una clase `Account` que sincroniza el acceso a su campo privado `balance` mediante el bloqueo de una instancia dedicada `balanceLock`.</span><span class="sxs-lookup"><span data-stu-id="65ce1-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="65ce1-122">El empleo de la misma instancia para bloquear garantiza que el campo `balance` no sea actualizado al mismo tiempo por dos subprocesos que intentan llamar a los métodos `Debit` o `Credit` simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="65ce1-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](snippets/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="65ce1-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="65ce1-123">C# language specification</span></span>

<span data-ttu-id="65ce1-124">Para más información, consulte la sección sobre la [instrucción lock](~/_csharplang/spec/statements.md#the-lock-statement) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="65ce1-124">For more information, see [The lock statement](~/_csharplang/spec/statements.md#the-lock-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65ce1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="65ce1-125">See also</span></span>

- [<span data-ttu-id="65ce1-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="65ce1-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="65ce1-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="65ce1-127">C# keywords</span></span>](index.md)
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="65ce1-128">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="65ce1-128">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
