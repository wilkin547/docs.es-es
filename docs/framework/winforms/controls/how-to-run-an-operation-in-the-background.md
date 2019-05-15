---
title: Procedimiento para ejecutar una operación en segundo plano
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
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591603"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="a2c04-102">Procedimiento para ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a2c04-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="a2c04-103">Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="a2c04-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="a2c04-104">El ejemplo de código siguiente muestra cómo ejecutar en segundo plano una operación que consume mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="a2c04-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="a2c04-105">El formulario cuenta con los botones **Iniciar** y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="a2c04-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="a2c04-106">Haga clic en el botón **Iniciar** para ejecutar una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a2c04-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="a2c04-107">Haga clic en el botón **Cancelar** para detener una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a2c04-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="a2c04-108">El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="a2c04-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="a2c04-109">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="a2c04-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="a2c04-110">Consulte también [Tutorial: Ejecución de una operación en segundo plano](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="a2c04-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2c04-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2c04-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2c04-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a2c04-112">Compiling the Code</span></span>  
 <span data-ttu-id="a2c04-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a2c04-113">This example requires:</span></span>  
  
- <span data-ttu-id="a2c04-114">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a2c04-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c04-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2c04-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="a2c04-116">Cómo: Implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a2c04-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="a2c04-117">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="a2c04-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)
