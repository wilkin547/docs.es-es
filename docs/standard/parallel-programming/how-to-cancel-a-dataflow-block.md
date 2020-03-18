---
title: 'Cómo: Cancelar un bloque de flujos de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
ms.openlocfilehash: aa175d95f27fcbf28c3f3da3eaa7b8f7988681e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140095"
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="aab1a-102">Cómo: Cancelar un bloque de flujos de datos</span><span class="sxs-lookup"><span data-stu-id="aab1a-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="aab1a-103">En este ejemplo se explica cómo habilitar la cancelación en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aab1a-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="aab1a-104">Este ejemplo usa Windows Forms para mostrar dónde están activos los elementos de trabajo en una canalización de flujo de datos y también los efectos de la canalización.</span><span class="sxs-lookup"><span data-stu-id="aab1a-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="aab1a-105">Para crear la aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aab1a-105">To Create the Windows Forms Application</span></span>  
  
1. <span data-ttu-id="aab1a-106">Cree un proyecto de **Aplicación de Windows Forms** de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="aab1a-106">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="aab1a-107">En los pasos siguientes, el proyecto se denomina `CancellationWinForms`.</span><span class="sxs-lookup"><span data-stu-id="aab1a-107">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2. <span data-ttu-id="aab1a-108">En el diseñador de formularios del formulario principal, Form1.cs (Form1.vb para Visual Basic), agregue un control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aab1a-108">On the form designer for the main form, Form1.cs (Form1.vb for Visual Basic), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3. <span data-ttu-id="aab1a-109">Agregue un control <xref:System.Windows.Forms.ToolStripButton> al control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aab1a-109">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="aab1a-110">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> y la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en **Agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-110">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4. <span data-ttu-id="aab1a-111">Agregue un segundo control <xref:System.Windows.Forms.ToolStripButton> al control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aab1a-111">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="aab1a-112">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en **Cancelar** y la propiedad <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> en `False`.</span><span class="sxs-lookup"><span data-stu-id="aab1a-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5. <span data-ttu-id="aab1a-113">Agregue cuatro objetos <xref:System.Windows.Forms.ToolStripProgressBar> al control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="aab1a-113">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="aab1a-114">Creación de la canalización de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="aab1a-114">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="aab1a-115">En esta sección se describe cómo crear la canalización de flujo de datos que procesa los elementos de trabajo y actualiza las barras de progreso.</span><span class="sxs-lookup"><span data-stu-id="aab1a-115">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="aab1a-116">Para crear la canalización de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="aab1a-116">To Create the Dataflow Pipeline</span></span>  
  
1. <span data-ttu-id="aab1a-117">En el proyecto, agregue una referencia a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="aab1a-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2. <span data-ttu-id="aab1a-118">Asegúrese de que Form1.cs (Form1.vb para Visual Basic) contenga las siguientes instrucciones `using` (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aab1a-118">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` statements (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3. <span data-ttu-id="aab1a-119">Agregue la clase `WorkItem` como un tipo interno de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="aab1a-119">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4. <span data-ttu-id="aab1a-120">Agregue a la clase `Form1` los miembros de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aab1a-120">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5. <span data-ttu-id="aab1a-121">Agregue el método siguiente, `CreatePipeline`, a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="aab1a-121">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="aab1a-122">Dado que los bloques de flujo de datos `incrementProgress` y `decrementProgress` actúan sobre la interfaz de usuario, es importante que esta acción se produzca en el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="aab1a-122">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="aab1a-123">Para lograrlo, durante la construcción, cada uno de estos objetos proporciona un objeto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> que tiene la propiedad <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> establecida como <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aab1a-123">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aab1a-124">El método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> crea un objeto <xref:System.Threading.Tasks.TaskScheduler> que funciona en el contexto de sincronización actual.</span><span class="sxs-lookup"><span data-stu-id="aab1a-124">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="aab1a-125">Dado que al constructor `Form1` se le llama desde el subproceso de interfaz de usuario, las acciones de los bloques de flujo de datos `incrementProgress` y `decrementProgress` se ejecutan también en el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="aab1a-125">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="aab1a-126">Este ejemplo establece la propiedad <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> cuando construye los miembros de la canalización.</span><span class="sxs-lookup"><span data-stu-id="aab1a-126">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="aab1a-127">Dado que la propiedad <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> cancela de forma permanente la ejecución del bloque de flujo de datos, se debe volver a crear la canalización completa después de que el usuario cancela la operación, en caso de que después desee agregar más elementos de trabajo a la canalización.</span><span class="sxs-lookup"><span data-stu-id="aab1a-127">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="aab1a-128">Para consultar un ejemplo en el que se muestre una forma alternativa de cancelar un bloque de flujo de datos, a fin de que se pueda realizar otro trabajo después de cancelar una operación, vea [Tutorial: uso de flujo de datos en una Aplicación de Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="aab1a-128">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="aab1a-129">Conexión de la canalización de flujo de datos a la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="aab1a-129">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="aab1a-130">En esta sección se describe cómo conectar la canalización de flujo de datos a la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="aab1a-130">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="aab1a-131">Tanto la creación de la canalización como la adición de elementos de trabajo a la canalización se controlan mediante el controlador de eventos para el botón **Agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-131">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="aab1a-132">La cancelación se inicia con el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-132">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="aab1a-133">Cuando el usuario hace clic en cualquiera de estos botones, se inicia la acción correspondiente de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="aab1a-133">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="aab1a-134">Para conectar la canalización de flujo de datos a la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="aab1a-134">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1. <span data-ttu-id="aab1a-135">En el diseñador de formularios del formulario principal, cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del botón **Agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-135">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2. <span data-ttu-id="aab1a-136">Implemente el evento <xref:System.Windows.Forms.ToolStripItem.Click> para el botón **Agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-136">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3. <span data-ttu-id="aab1a-137">En el diseñador de formularios del formulario principal, cree un controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="aab1a-138">Implemente el controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="aab1a-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="aab1a-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aab1a-139">Example</span></span>  
 <span data-ttu-id="aab1a-140">En el siguiente ejemplo se muestra el código completo de Form1.cs (Form1.vb para Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aab1a-140">The following example shows the complete code for Form1.cs (Form1.vb for Visual Basic).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="aab1a-141">En la ilustración siguiente se muestra la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="aab1a-141">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="aab1a-142">![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="aab1a-142">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  

## <a name="see-also"></a><span data-ttu-id="aab1a-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="aab1a-143">See also</span></span>

- [<span data-ttu-id="aab1a-144">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="aab1a-144">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
