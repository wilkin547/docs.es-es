---
title: Procedimiento para ejecutar una operación en segundo plano
description: Aprenda a usar la clase BackgroundWorker para ejecutar una operación de Windows Forms que consume mucho tiempo en segundo plano.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621579"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="e7703-103">Procedimiento para ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="e7703-103">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="e7703-104">Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="e7703-104">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="e7703-105">El ejemplo de código siguiente muestra cómo ejecutar en segundo plano una operación que consume mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="e7703-105">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="e7703-106">El formulario cuenta con los botones **Iniciar** y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e7703-106">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="e7703-107">Haga clic en el botón **Iniciar** para ejecutar una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e7703-107">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="e7703-108">Haga clic en el botón **Cancelar** para detener una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e7703-108">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="e7703-109">El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e7703-109">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="e7703-110">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="e7703-110">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="e7703-111">Vea también [Tutorial: Ejecutar una operación en segundo plano](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="e7703-111">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7703-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7703-112">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7703-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e7703-113">Compiling the Code</span></span>  
 <span data-ttu-id="e7703-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e7703-114">This example requires:</span></span>  
  
- <span data-ttu-id="e7703-115">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e7703-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7703-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7703-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="e7703-117">Procedimiento para implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="e7703-117">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="e7703-118">BackgroundWorker (Componente)</span><span class="sxs-lookup"><span data-stu-id="e7703-118">BackgroundWorker Component</span></span>](backgroundworker-component.md)
