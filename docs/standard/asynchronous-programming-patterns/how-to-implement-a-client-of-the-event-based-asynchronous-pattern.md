---
title: "Cómo: Implementar un cliente en un modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f8069072f5d917d4ef169a1aed8854ae3139016d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="53551-102">Cómo: Implementar un cliente en un modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="53551-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="53551-103">En el ejemplo de código siguiente se muestra cómo utilizar un componente que se adhiera a la [Información general sobre el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="53551-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="53551-104">En el formulario de este ejemplo se usa el componente `PrimeNumberCalculator` descrito en [Implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="53551-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="53551-105">Cuando se ejecuta un proyecto que usa este ejemplo, verá un formulario "Prime Number Calculator" (Calculadora de número primo) con una cuadrícula y dos botones: **Start New Task** (Iniciar nueva tarea) y **Cancel** (Cancelar).</span><span class="sxs-lookup"><span data-stu-id="53551-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="53551-106">Puede hacer clic en el botón **Start New Task** (Iniciar nueva tarea) varias veces seguidas, y por cada clic, una operación asincrónica iniciará un cálculo para determinar si un número de prueba generado aleatoriamente es primo.</span><span class="sxs-lookup"><span data-stu-id="53551-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="53551-107">El formulario mostrará periódicamente el progreso y los resultados incrementales.</span><span class="sxs-lookup"><span data-stu-id="53551-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="53551-108">A cada operación se le asigna un identificador de tarea único.</span><span class="sxs-lookup"><span data-stu-id="53551-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="53551-109">El resultado del cálculo se muestra en la columna **Result** (Resultado); si el número de prueba no es primo, se etiqueta como **Composite** (Compuesto) y se muestra su primer divisor.</span><span class="sxs-lookup"><span data-stu-id="53551-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="53551-110">Cualquier operación pendiente puede cancelarse con el botón **Cancel** (Cancelar).</span><span class="sxs-lookup"><span data-stu-id="53551-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="53551-111">Se pueden realizar selecciones múltiples.</span><span class="sxs-lookup"><span data-stu-id="53551-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53551-112">La mayoría de los números no serán primos.</span><span class="sxs-lookup"><span data-stu-id="53551-112">Most numbers will not be prime.</span></span> <span data-ttu-id="53551-113">Si no ha encontrado un número primo tras realizar varias operaciones, simplemente inicie más tareas y, finalmente, encontrará algunos números primos.</span><span class="sxs-lookup"><span data-stu-id="53551-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53551-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53551-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="53551-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="53551-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
