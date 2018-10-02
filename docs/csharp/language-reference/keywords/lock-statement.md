---
title: lock (Instrucción, Referencia de C#)
description: Use la instrucción lock de C# para sincronizar el acceso de un subproceso al recurso compartido
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858361"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="979c9-103">lock (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="979c9-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="979c9-104">La instrucción `lock` obtiene el bloqueo de exclusión mutua de un objeto determinado, ejecuta un bloque de instrucciones y luego libera el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="979c9-104">The `lock` statement obtains the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="979c9-105">Mientras se mantiene un bloqueo, el subproceso que lo mantiene puede volver a obtener y liberar el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="979c9-105">While a lock is held, the thread that holds the lock can again obtain and release the lock.</span></span> <span data-ttu-id="979c9-106">Ningún otro subproceso puede obtener el bloqueo y espera hasta que se libera.</span><span class="sxs-lookup"><span data-stu-id="979c9-106">Any other thread is blocked from obtaining the lock and waits until the lock is released.</span></span>

<span data-ttu-id="979c9-107">La instrucción `lock` tiene el formato</span><span class="sxs-lookup"><span data-stu-id="979c9-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="979c9-108">donde `x` es una expresión de un [tipo de referencia](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="979c9-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="979c9-109">Es exactamente equivalente a</span><span class="sxs-lookup"><span data-stu-id="979c9-109">It's precisely equivalent to</span></span>

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

<span data-ttu-id="979c9-110">Puesto que el código usa un bloque [try... finally](try-finally.md), el bloqueo se libera aunque se produzca una excepción dentro del cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="979c9-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="979c9-111">No se puede usar la palabra clave [await](await.md) en el cuerpo de una instrucción `lock`.</span><span class="sxs-lookup"><span data-stu-id="979c9-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="979c9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="979c9-112">Remarks</span></span>

<span data-ttu-id="979c9-113">Al sincronizar el acceso del subproceso al recurso compartido, bloquee una instancia dedicada de objeto (por ejemplo, `private readonly object balanceLock = new object();`) u otra instancia cuyo empleo como objeto de bloqueo sea poco probable por parte de elementos no relacionados del código.</span><span class="sxs-lookup"><span data-stu-id="979c9-113">When you synchronize thread access to shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="979c9-114">Evite el uso de la misma instancia de objeto de bloqueo para distintos recursos compartidos, ya que se podría producir un interbloqueo o una contención de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="979c9-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="979c9-115">En particular, evite usar</span><span class="sxs-lookup"><span data-stu-id="979c9-115">In particular, avoid using</span></span>

- <span data-ttu-id="979c9-116">`this` (los autores de llamadas podrían usarlo como un bloqueo),</span><span class="sxs-lookup"><span data-stu-id="979c9-116">`this` (might be used by the callers as a lock),</span></span>
- <span data-ttu-id="979c9-117">instancias <xref:System.Type> (el operador o la reflexión [typeof](typeof.md) podrían obtenerlas),</span><span class="sxs-lookup"><span data-stu-id="979c9-117"><xref:System.Type> instances (might be obtained by the [typeof](typeof.md) operator or reflection),</span></span>
- <span data-ttu-id="979c9-118">instancias de cadena, incluidos literales de cadena,</span><span class="sxs-lookup"><span data-stu-id="979c9-118">string instances, including string literals,</span></span>

<span data-ttu-id="979c9-119">como objetos de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="979c9-119">as lock objects.</span></span>

## <a name="example"></a><span data-ttu-id="979c9-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="979c9-120">Example</span></span>

<span data-ttu-id="979c9-121">En el ejemplo siguiente se define una clase `Account` que sincroniza el acceso a su campo privado `balance` mediante el bloqueo de una instancia dedicada `balanceLock`.</span><span class="sxs-lookup"><span data-stu-id="979c9-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="979c9-122">El empleo de la misma instancia para bloquear garantiza que el campo `balance` no sea actualizado al mismo tiempo por dos subprocesos que intentan llamar a los métodos `Debit` o `Credit` simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="979c9-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="979c9-123">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="979c9-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="979c9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="979c9-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="979c9-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="979c9-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="979c9-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="979c9-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="979c9-127">Palabras clave de instrucciones</span><span class="sxs-lookup"><span data-stu-id="979c9-127">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="979c9-128">Operaciones de bloqueo</span><span class="sxs-lookup"><span data-stu-id="979c9-128">Interlocked operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="979c9-129">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="979c9-129">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)