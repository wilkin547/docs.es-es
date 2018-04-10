---
title: Modelos para la programación asincrónica
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42298bc8e3101b03f6c3e03fec453b72cd959efb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="3057e-102">Modelos para la programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="3057e-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="3057e-103">.NET Framework proporciona tres patrones para realizar las operaciones asincrónicas:</span><span class="sxs-lookup"><span data-stu-id="3057e-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="3057e-104">El patrón de programación asincrónica (APM) (también llamado patrón <xref:System.IAsyncResult>), en el que las operaciones asincrónicas requieren los métodos `Begin` y `End` (por ejemplo, `BeginWrite` y `EndWrite` para las operaciones asincrónicas de escritura).</span><span class="sxs-lookup"><span data-stu-id="3057e-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="3057e-105">Este patrón ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3057e-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="3057e-106">Para más información, consulte [Modelo de programación asincrónica (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="3057e-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="3057e-107">El patrón asincrónico basado en eventos (EAP), que requiere un método que tiene el sufijo `Async` y también uno o más eventos, tipos de delegado de controlador de eventos y tipos derivados de `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="3057e-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="3057e-108">EAP apareció por primera vez en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3057e-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="3057e-109">Ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3057e-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="3057e-110">Para más información, consulte [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="3057e-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="3057e-111">El patrón asincrónico basado en tareas (TAP), que utiliza un método único para representar el inicio y la finalización de una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="3057e-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="3057e-112">TAP se introdujo en .NET Framework 4 y es el método recomendado para programación asincrónica en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3057e-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="3057e-113">Las palabras clave [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) en C# y los operadores [Async y](~/docs/visual-basic/language-reference/modifiers/async.md) [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic agregan compatibilidad de lenguaje para TAP.</span><span class="sxs-lookup"><span data-stu-id="3057e-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="3057e-114">Para más información, consulte [Patrón asincrónico basado en tareas (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="3057e-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="3057e-115">Comparación de patrones</span><span class="sxs-lookup"><span data-stu-id="3057e-115">Comparing Patterns</span></span>  

<span data-ttu-id="3057e-116">Para una comparación rápida de cómo los tres patrones modelan las operaciones asincrónicas, considere un método `Read` que lea una determinada cantidad de datos en un búfer proporcionado comenzando en un desplazamiento especificado:</span><span class="sxs-lookup"><span data-stu-id="3057e-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="3057e-117">El equivalente de APM para este método expondría los métodos `BeginRead` y `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="3057e-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="3057e-118">El equivalente EAP expondría el siguiente conjunto de tipos y miembros:</span><span class="sxs-lookup"><span data-stu-id="3057e-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="3057e-119">El equivalente TAP expondría el siguiente método `ReadAsync` único:</span><span class="sxs-lookup"><span data-stu-id="3057e-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="3057e-120">Para obtener información completa sobre TAP, APM y EAP, consulte los vínculos de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3057e-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="3057e-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3057e-121">Related topics</span></span>

| <span data-ttu-id="3057e-122">Title</span><span class="sxs-lookup"><span data-stu-id="3057e-122">Title</span></span> | <span data-ttu-id="3057e-123">Description</span><span class="sxs-lookup"><span data-stu-id="3057e-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="3057e-124">Modelo para la programación asincrónica (APM)</span><span class="sxs-lookup"><span data-stu-id="3057e-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="3057e-125">Describe el patrón heredado que utiliza la interfaz <xref:System.IAsyncResult> para proporcionar un comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3057e-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="3057e-126">Este patrón ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3057e-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="3057e-127">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="3057e-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="3057e-128">Describe el patrón heredado basado en eventos para proporcionar el comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3057e-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="3057e-129">Este patrón ya no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3057e-129">This model is no longer recommended for new development.</span></span> |
| <span data-ttu-id="3057e-130">[Modelo asincrónico basado en tareas [TAP]](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span><span class="sxs-lookup"><span data-stu-id="3057e-130">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span> | <span data-ttu-id="3057e-131">Describe el nuevo patrón asincrónico basado en el espacio de nombres <xref:System.Threading.Tasks>.</span><span class="sxs-lookup"><span data-stu-id="3057e-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="3057e-132">Este patrón es el método recomendado para la programación asincrónica en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3057e-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3057e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3057e-133">See also</span></span>

<span data-ttu-id="3057e-134">[Programación asincrónica en C#](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="3057e-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="3057e-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)  (Programación asincrónica en F#)</span><span class="sxs-lookup"><span data-stu-id="3057e-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="3057e-136">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3057e-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
