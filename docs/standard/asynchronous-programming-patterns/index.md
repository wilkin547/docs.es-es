---
title: Patrones para la programación asincrónica
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: e1efe9c3eb57f317def91e527506c358eb086679
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160058"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="622ba-102">Patrones para la programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="622ba-102">Asynchronous programming patterns</span></span>

<span data-ttu-id="622ba-103">.NET proporciona tres patrones para realizar las operaciones asincrónicas:</span><span class="sxs-lookup"><span data-stu-id="622ba-103">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="622ba-104">**Patrón asincrónico basado en tareas (TAP)** , que utiliza un método único para representar el inicio y la finalización de una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="622ba-104">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="622ba-105">TAP apareció por primera vez en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="622ba-105">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="622ba-106">**Es el enfoque recomendado para la programación asincrónica en. NET.**</span><span class="sxs-lookup"><span data-stu-id="622ba-106">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="622ba-107">Las palabras clave [2.async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) en C# y los operadores [Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic agregan compatibilidad de lenguaje para TAP.</span><span class="sxs-lookup"><span data-stu-id="622ba-107">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="622ba-108">Para más información, consulte [Patrón asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="622ba-108">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="622ba-109">El **modelo asincrónico basado en eventos (EAP)** , que es el patrón heredado basado en eventos para proporcionar el comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="622ba-109">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="622ba-110">Requiere un método con el sufijo `Async`, así como uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="622ba-110">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="622ba-111">EAP apareció por primera vez en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="622ba-111">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="622ba-112">Ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="622ba-112">It's no longer recommended for new development.</span></span> <span data-ttu-id="622ba-113">Para más información, consulte [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="622ba-113">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="622ba-114">El patrón **Modelo de programación asincrónica (APM)** (también denominado <xref:System.IAsyncResult>), que es el modelo heredado que usa la interfaz <xref:System.IAsyncResult> para ofrecer un comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="622ba-114">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="622ba-115">En este patrón, las operaciones sincrónicas requieren los métodos `Begin` y `End` (por ejemplo, `BeginWrite` y `EndWrite` para implementar una operación de escritura asincrónica).</span><span class="sxs-lookup"><span data-stu-id="622ba-115">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="622ba-116">Este patrón ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="622ba-116">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="622ba-117">Para más información, consulte [Modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="622ba-117">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="622ba-118">Comparación de patrones</span><span class="sxs-lookup"><span data-stu-id="622ba-118">Comparison of patterns</span></span>

<span data-ttu-id="622ba-119">Para una comparación rápida de cómo los tres patrones modelan las operaciones asincrónicas, considere un método `Read` que lea una determinada cantidad de datos en un búfer proporcionado comenzando en un desplazamiento especificado:</span><span class="sxs-lookup"><span data-stu-id="622ba-119">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="622ba-120">El equivalente TAP de este método expondría el siguiente método `ReadAsync` único:</span><span class="sxs-lookup"><span data-stu-id="622ba-120">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="622ba-121">El equivalente EAP expondría el siguiente conjunto de tipos y miembros:</span><span class="sxs-lookup"><span data-stu-id="622ba-121">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="622ba-122">El equivalente APM expondría los métodos `BeginRead` y `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="622ba-122">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="622ba-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="622ba-123">See also</span></span>

- [<span data-ttu-id="622ba-124">Async en profundidad</span><span class="sxs-lookup"><span data-stu-id="622ba-124">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="622ba-125">Programación asincrónica en C#</span><span class="sxs-lookup"><span data-stu-id="622ba-125">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="622ba-126">Programación asincrónica en F#</span><span class="sxs-lookup"><span data-stu-id="622ba-126">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="622ba-127">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="622ba-127">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
