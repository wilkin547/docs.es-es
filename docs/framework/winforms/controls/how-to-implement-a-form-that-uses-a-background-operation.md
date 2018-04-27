---
title: 'Cómo: Implementar un formulario que utiliza una operación en segundo plano'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 416e7e1a4a380e13c9b3f776bc8e31812b217c51
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="53c29-102">Cómo: Implementar un formulario que utiliza una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="53c29-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="53c29-103">El programa de ejemplo siguiente crea un formulario que calcula los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="53c29-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="53c29-104">El cálculo se ejecuta en un subproceso independiente del subproceso de interfaz de usuario, por lo que la interfaz de usuario sigue ejecutándose sin retrasos mientras se realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="53c29-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="53c29-105">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="53c29-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="53c29-106">Vea también [Tutorial: Implementar un formulario que utiliza una operación en segundo plano](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="53c29-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53c29-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53c29-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53c29-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="53c29-108">Compiling the Code</span></span>  
 <span data-ttu-id="53c29-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="53c29-109">This example requires:</span></span>  
  
-   <span data-ttu-id="53c29-110">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="53c29-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="53c29-111">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="53c29-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="53c29-112">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="53c29-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="53c29-113">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="53c29-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="53c29-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="53c29-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="53c29-115">Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.</span><span class="sxs-lookup"><span data-stu-id="53c29-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="53c29-116">Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.</span><span class="sxs-lookup"><span data-stu-id="53c29-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c29-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="53c29-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="53c29-118">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="53c29-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="53c29-119">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="53c29-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
