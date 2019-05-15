---
title: Procedimiento para implementar un formulario que usa una operación en segundo plano
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: df7c6caf7b23824a596e94e1bd62205907b0b56a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592411"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="4fcd2-102">Procedimiento para implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="4fcd2-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="4fcd2-103">El programa de ejemplo siguiente crea un formulario que calcula los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="4fcd2-104">El cálculo se ejecuta en un subproceso independiente del subproceso de interfaz de usuario, por lo que la interfaz de usuario sigue ejecutándose sin retrasos mientras se realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="4fcd2-105">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="4fcd2-106">Consulte también [Tutorial: Implementar un formulario que utiliza una operación en segundo plano](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4fcd2-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fcd2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fcd2-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4fcd2-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4fcd2-108">Compiling the Code</span></span>  
 <span data-ttu-id="4fcd2-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4fcd2-109">This example requires:</span></span>  
  
- <span data-ttu-id="4fcd2-110">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4fcd2-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4fcd2-111">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4fcd2-112">Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="4fcd2-113">Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.</span><span class="sxs-lookup"><span data-stu-id="4fcd2-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcd2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fcd2-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="4fcd2-115">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="4fcd2-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="4fcd2-116">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="4fcd2-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
