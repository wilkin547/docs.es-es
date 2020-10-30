---
title: Patrones para la programación asincrónica
description: Obtenga información sobre el patrón asincrónico basado en tareas (TAP), el patrón asincrónico basado en eventos (EAP) y el modelo de programación asincrónica (APM) en .NET.
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
ms.openlocfilehash: d8a68295836fb1e87ab82425ab0973fc1b65f4b2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888768"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="096ab-103">Patrones para la programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="096ab-103">Asynchronous programming patterns</span></span>

<span data-ttu-id="096ab-104">.NET proporciona tres patrones para realizar las operaciones asincrónicas:</span><span class="sxs-lookup"><span data-stu-id="096ab-104">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="096ab-105">**Patrón asincrónico basado en tareas (TAP)** , que utiliza un método único para representar el inicio y la finalización de una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="096ab-105">**Task-based Asynchronous Pattern (TAP)** , which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="096ab-106">TAP Se presentó en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="096ab-106">TAP was introduced in .NET Framework 4.</span></span> <span data-ttu-id="096ab-107">**Es el enfoque recomendado para la programación asincrónica en. NET.**</span><span class="sxs-lookup"><span data-stu-id="096ab-107">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="096ab-108">Las palabras clave [2.async](../../csharp/language-reference/keywords/async.md) y [await](../../csharp/language-reference/operators/await.md) en C# y los operadores [Async](../../visual-basic/language-reference/modifiers/async.md) y [Await](../../visual-basic/language-reference/operators/await-operator.md) en Visual Basic agregan compatibilidad de lenguaje para TAP.</span><span class="sxs-lookup"><span data-stu-id="096ab-108">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="096ab-109">Para más información, consulte [Patrón asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="096ab-109">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="096ab-110">El **modelo asincrónico basado en eventos (EAP)** , que es el patrón heredado basado en eventos para proporcionar el comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="096ab-110">**Event-based Asynchronous Pattern (EAP)** , which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="096ab-111">Requiere un método con el sufijo `Async`, así como uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="096ab-111">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="096ab-112">EAP se presentó en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="096ab-112">EAP was introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="096ab-113">Ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="096ab-113">It's no longer recommended for new development.</span></span> <span data-ttu-id="096ab-114">Para más información, consulte [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="096ab-114">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="096ab-115">El patrón **Modelo de programación asincrónica (APM)** (también denominado <xref:System.IAsyncResult>), que es el modelo heredado que usa la interfaz <xref:System.IAsyncResult> para ofrecer un comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="096ab-115">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="096ab-116">En este patrón, las operaciones sincrónicas requieren los métodos `Begin` y `End` (por ejemplo, `BeginWrite` y `EndWrite` para implementar una operación de escritura asincrónica).</span><span class="sxs-lookup"><span data-stu-id="096ab-116">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="096ab-117">Este patrón ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="096ab-117">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="096ab-118">Para más información, consulte [Modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="096ab-118">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="096ab-119">Comparación de patrones</span><span class="sxs-lookup"><span data-stu-id="096ab-119">Comparison of patterns</span></span>

<span data-ttu-id="096ab-120">Para una comparación rápida de cómo los tres patrones modelan las operaciones asincrónicas, considere un método `Read` que lea una determinada cantidad de datos en un búfer proporcionado comenzando en un desplazamiento especificado:</span><span class="sxs-lookup"><span data-stu-id="096ab-120">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="096ab-121">El equivalente TAP de este método expondría el siguiente método `ReadAsync` único:</span><span class="sxs-lookup"><span data-stu-id="096ab-121">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="096ab-122">El equivalente EAP expondría el siguiente conjunto de tipos y miembros:</span><span class="sxs-lookup"><span data-stu-id="096ab-122">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="096ab-123">El equivalente APM expondría los métodos `BeginRead` y `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="096ab-123">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="096ab-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="096ab-124">See also</span></span>

- [<span data-ttu-id="096ab-125">Async en profundidad</span><span class="sxs-lookup"><span data-stu-id="096ab-125">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="096ab-126">Programación asincrónica en C#</span><span class="sxs-lookup"><span data-stu-id="096ab-126">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="096ab-127">Programación asincrónica en F#</span><span class="sxs-lookup"><span data-stu-id="096ab-127">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="096ab-128">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="096ab-128">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
