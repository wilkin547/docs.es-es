---
title: "How to: Cancel a Dataflow Block | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "dataflow blocks, canceling in TPL"
  - "TPL dataflow library,canceling dataflow blocks"
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Cancel a Dataflow Block
En este documento se muestra cómo habilitar la cancelación de la aplicación.  Este ejemplo utiliza formularios Windows Forms para mostrar donde están activos los elementos de trabajo en una canalización de flujo de datos y también los efectos de cancelación.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
### Para crear la aplicación de Windows Forms  
  
1.  Cree un proyecto de C\# o Visual Basic **Aplicación de Windows Forms** .  En los siguientes pasos, el proyecto se denomina `CancellationWinForms`.  
  
2.  En el diseñador de formularios para el formulario principal, Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), agregue un control de <xref:System.Windows.Forms.ToolStrip> .  
  
3.  Agregue un control de <xref:System.Windows.Forms.ToolStripButton> al control de <xref:System.Windows.Forms.ToolStrip> .  Establezca la propiedad de <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle> y la propiedad de <xref:System.Windows.Forms.ToolStripItem.Text%2A> para agregar elementos de trabajo.  
  
4.  Agregue un control de <xref:System.Windows.Forms.ToolStripButton> de segundo al control de <xref:System.Windows.Forms.ToolStrip> .  Establezca la propiedad de <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, la propiedad de <xref:System.Windows.Forms.ToolStripItem.Text%2A> para cancelar, y la propiedad de <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> a `False`.  
  
5.  Agregue cuatro objetos de <xref:> System.Windows.Forms.ToolStripProgressBar?qualifyHint=False&autoUpgrade=True al control de <xref:System.Windows.Forms.ToolStrip> .  
  
## Crear la canalización de flujo de datos  
 En esta sección se describe cómo crear la canalización de flujo de datos que los elementos de trabajo de procesos y actualiza las barras de progreso.  
  
#### Para crear la canalización de flujo de datos  
  
1.  En el proyecto, agregue una referencia a System.Threading.Tasks.Dataflow.dll.  
  
2.  Asegúrese de que Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) contiene las siguientes instrucciones de `using` \(`Imports` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Agregue la clase de `WorkItem` como tipo interno de la clase de `Form1` .  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Agregue a la clase `Form1` los miembros de datos siguientes:  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Agregue el método siguiente, `CreatePipeline`, a la clase de `Form1` .  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Dado que los bloques de flujo de datos de `incrementProgress` y de `decrementProgress` representar en la interfaz de usuario, es importante que estas acciones aparecen en el subproceso de interfaz de usuario.  Para ello, durante la construcción estos objetos cada proporcionan un objeto de <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> que tiene la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> establecida en <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>.  El método de <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> crea un objeto de <xref:System.Threading.Tasks.TaskScheduler> que realice el trabajo en el contexto de sincronización.  Dado que se llama al constructor de `Form1` el subproceso, acciones para los bloques de flujo de datos de `incrementProgress` y de `decrementProgress` también se ejecutan en el subproceso de interfaz de usuario.  
  
 Este ejemplo establece la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> cuando construye los miembros de la canalización.  Dado que la propiedad de <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> cancela permanentemente la ejecución del bloque de flujo de datos, la canalización de conjunto debe volver a crear después de que el usuario cancele la operación y la desee agregar más elementos de trabajo a la canalización.  Para obtener un ejemplo que muestra una manera alternativa de cancelar un flujo de datos incrustado para poder realizar otro trabajo después de que una operación está cancelado, vea [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## Conexión de canalización de flujo de datos con la interfaz de usuario  
 Esta sección describe cómo conectar la canalización de flujo de datos a la interfaz de usuario.  Creando la canalización y agregando elementos de trabajo a la canalización son controlados por el controlador de eventos para el botón de los elementos de trabajo add.  La cancelación es iniciada por el botón Cancelar.  Cuando el usuario hace clic en cualquiera de ellos, la acción adecuada se inicia de forma asincrónica.  
  
#### Para conectar la canalización de flujo de datos a la interfaz de usuario  
  
1.  En el diseñador de formularios para el formulario principal, cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> para el botón de los elementos de trabajo add.  
  
2.  Implemente el evento de <xref:System.Windows.Forms.ToolStripItem.Click> para el botón de los elementos de trabajo add.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  En el diseñador de formularios para el formulario principal, cree un controlador de eventos para el controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para el botón cancel.  
  
4.  Implemente el controlador de eventos de <xref:System.Windows.Forms.ToolStripItem.Click> para el botón cancel.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra el código completo de Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 La ilustración siguiente muestra la aplicación en ejecución.  
  
 ![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow\_Cancellation")  
  
## Programación eficaz  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)