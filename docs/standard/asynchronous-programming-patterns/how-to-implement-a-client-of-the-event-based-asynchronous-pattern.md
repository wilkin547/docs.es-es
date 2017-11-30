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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="510db-102">Cómo: Implementar un cliente en un modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="510db-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="510db-103">En el ejemplo de código siguiente se muestra cómo utilizar un componente que se adhiera a la [introducción de patrón asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="510db-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="510db-104">El formulario en este ejemplo usa el `PrimeNumberCalculator` componente se describe en [Cómo: implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="510db-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="510db-105">Cuando se ejecuta un proyecto que se usa en este ejemplo, verá un formulario de "Calculadora de número primo" con una cuadrícula y dos botones: **Iniciar nueva tarea** y **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="510db-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="510db-106">Puede hacer clic en el **Iniciar nueva tarea** botón varias veces seguidas, y por cada clic, una operación asincrónica iniciará un cálculo para determinar si un número generado aleatoriamente prueba es primo.</span><span class="sxs-lookup"><span data-stu-id="510db-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="510db-107">El formulario mostrará periódicamente el progreso y resultados incrementales.</span><span class="sxs-lookup"><span data-stu-id="510db-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="510db-108">Cada operación se le asigna un identificador de tarea único.</span><span class="sxs-lookup"><span data-stu-id="510db-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="510db-109">El resultado del cálculo se muestra en el **resultado** columna; si el número de prueba no es primo, se etiqueta como **compuesto,** y se muestra su primer divisor.</span><span class="sxs-lookup"><span data-stu-id="510db-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="510db-110">Cualquier operación pendiente puede cancelarse con el **cancelar** botón.</span><span class="sxs-lookup"><span data-stu-id="510db-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="510db-111">Se pueden realizar selecciones múltiples.</span><span class="sxs-lookup"><span data-stu-id="510db-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="510db-112">Casi todos los números no serán primos.</span><span class="sxs-lookup"><span data-stu-id="510db-112">Most numbers will not be prime.</span></span> <span data-ttu-id="510db-113">Si no ha encontrado un número primo tras realizar varias operaciones, simplemente inicie más tareas y, finalmente, encontrará algunos números primos.</span><span class="sxs-lookup"><span data-stu-id="510db-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="510db-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="510db-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="510db-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="510db-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
