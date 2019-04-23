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
ms.openlocfilehash: 98d51f9c6465186e77784aba080130110545f399
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192165"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="962d3-102">Procedimiento para implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="962d3-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="962d3-103">El programa de ejemplo siguiente crea un formulario que calcula los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="962d3-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="962d3-104">El cálculo se ejecuta en un subproceso independiente del subproceso de interfaz de usuario, por lo que la interfaz de usuario sigue ejecutándose sin retrasos mientras se realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="962d3-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="962d3-105">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="962d3-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="962d3-106">Consulte también [Tutorial: Implementar un formulario que utiliza una operación en segundo plano](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="962d3-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="962d3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="962d3-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="962d3-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="962d3-108">Compiling the Code</span></span>  
 <span data-ttu-id="962d3-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="962d3-109">This example requires:</span></span>  
  
-   <span data-ttu-id="962d3-110">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="962d3-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="962d3-111">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="962d3-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="962d3-112">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="962d3-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="962d3-113">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="962d3-113">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="962d3-114">Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.</span><span class="sxs-lookup"><span data-stu-id="962d3-114">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="962d3-115">Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.</span><span class="sxs-lookup"><span data-stu-id="962d3-115">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962d3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="962d3-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="962d3-117">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="962d3-117">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="962d3-118">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="962d3-118">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
