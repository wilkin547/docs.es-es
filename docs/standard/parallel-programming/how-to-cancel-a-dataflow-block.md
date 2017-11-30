---
title: "Cómo: Cancelar un bloque de flujos de datos"
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
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="ee1d5-102">Cómo: Cancelar un bloque de flujos de datos</span><span class="sxs-lookup"><span data-stu-id="ee1d5-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="ee1d5-103">En este ejemplo se explica cómo habilitar la cancelación en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="ee1d5-104">Este ejemplo usa Windows Forms para mostrar dónde están activos los elementos de trabajo en una canalización de flujo de datos y también los efectos de la canalización.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ee1d5-105">La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee1d5-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="ee1d5-106">Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="ee1d5-107">Para crear la aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee1d5-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="ee1d5-108">Cree un proyecto de **Aplicación de Windows Forms** de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="ee1d5-109">En los pasos siguientes, el proyecto se denomina `CancellationWinForms`.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="ee1d5-110">En el Diseñador de formularios para el formulario principal, Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), agregue un <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="ee1d5-111">Agregar un <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ee1d5-112">Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad a <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> y <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="ee1d5-113">Agregue un segundo <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ee1d5-114">Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **cancelar**y el <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> propiedad para `False`.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="ee1d5-115">Agregue cuatro <xref:System.Windows.Forms.ToolStripProgressBar> objetos a la <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="ee1d5-116">Creación de la canalización de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="ee1d5-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="ee1d5-117">En esta sección se describe cómo crear la canalización de flujo de datos que procesa los elementos de trabajo y actualiza las barras de progreso.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="ee1d5-118">Para crear la canalización de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="ee1d5-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="ee1d5-119">En el proyecto, agregue una referencia a System.Threading.Tasks.Dataflow.dll.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="ee1d5-120">Asegúrese de que Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contenga las siguientes instrucciones `using` (`Imports` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ee1d5-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="ee1d5-121">Agregue la clase `WorkItem` como un tipo interno de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="ee1d5-122">Agregue a la clase `Form1` los miembros de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ee1d5-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="ee1d5-123">Agregue el método siguiente, `CreatePipeline`, a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="ee1d5-124">Dado que los bloques de flujo de datos `incrementProgress` y `decrementProgress` actúan sobre la interfaz de usuario, es importante que esta acción se produzca en el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="ee1d5-125">Para lograr esto, opción durante la construcción de estos objetos cada uno de ellos proporcionan un <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> objeto que tiene el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> propiedad establecida en <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee1d5-126">El método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> crea un objeto <xref:System.Threading.Tasks.TaskScheduler> que funciona en el contexto de sincronización actual.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="ee1d5-127">Dado que al constructor `Form1` se le llama desde el subproceso de interfaz de usuario, las acciones de los bloques de flujo de datos `incrementProgress` y `decrementProgress` se ejecutan también en el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="ee1d5-128">Este ejemplo se establece la <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad cuando construye los miembros de la canalización.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="ee1d5-129">Dado que el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad permanentemente cancela la ejecución de bloques de flujo de datos, debe volver a crearse la canalización completa cuando el usuario cancela la operación y, a continuación, desea agregar más elementos de trabajo a la canalización.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="ee1d5-130">Para consultar un ejemplo en el que se muestre una forma alternativa de cancelar un bloque de flujo de datos, a fin de que se pueda realizar otro trabajo después de cancelar una operación, vea [Tutorial: uso de flujo de datos en una Aplicación de Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="ee1d5-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ee1d5-131">Conexión de la canalización de flujo de datos a la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ee1d5-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="ee1d5-132">En esta sección se describe cómo conectar la canalización de flujo de datos a la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="ee1d5-133">Tanto la creación de la canalización como la adición de elementos de trabajo a la canalización se controlan mediante el controlador de eventos para el botón **Agregar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="ee1d5-134">La cancelación se inicia con el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="ee1d5-135">Cuando el usuario hace clic en cualquiera de estos botones, se inicia la acción correspondiente de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ee1d5-136">Para conectar la canalización de flujo de datos a la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ee1d5-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="ee1d5-137">En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **agregar elementos de trabajo** botón.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="ee1d5-138">Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **agregar elementos de trabajo** botón.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="ee1d5-139">En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para el **cancelar** botón.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="ee1d5-140">Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para el **cancelar** botón.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="ee1d5-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee1d5-141">Example</span></span>  
 <span data-ttu-id="ee1d5-142">En el siguiente ejemplo, se muestra el código completo de Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ee1d5-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="ee1d5-143">En la ilustración siguiente se muestra la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee1d5-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="ee1d5-144">![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="ee1d5-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ee1d5-145">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ee1d5-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1d5-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee1d5-146">See Also</span></span>  
 [<span data-ttu-id="ee1d5-147">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="ee1d5-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
