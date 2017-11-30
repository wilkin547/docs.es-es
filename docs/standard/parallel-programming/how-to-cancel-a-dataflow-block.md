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
# <a name="how-to-cancel-a-dataflow-block"></a>Cómo: Cancelar un bloque de flujos de datos
En este ejemplo se explica cómo habilitar la cancelación en la aplicación. Este ejemplo usa Windows Forms para mostrar dónde están activos los elementos de trabajo en una canalización de flujo de datos y también los efectos de la canalización.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
### <a name="to-create-the-windows-forms-application"></a>Para crear la aplicación de Windows Forms  
  
1.  Cree un proyecto de **Aplicación de Windows Forms** de Visual Basic o C#. En los pasos siguientes, el proyecto se denomina `CancellationWinForms`.  
  
2.  En el Diseñador de formularios para el formulario principal, Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), agregue un <xref:System.Windows.Forms.ToolStrip> control.  
  
3.  Agregar un <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control. Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad a <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> y <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **agregar elementos de trabajo**.  
  
4.  Agregue un segundo <xref:System.Windows.Forms.ToolStripButton> el control a la <xref:System.Windows.Forms.ToolStrip> control. Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad **cancelar**y el <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> propiedad para `False`.  
  
5.  Agregue cuatro <xref:System.Windows.Forms.ToolStripProgressBar> objetos a la <xref:System.Windows.Forms.ToolStrip> control.  
  
## <a name="creating-the-dataflow-pipeline"></a>Creación de la canalización de flujo de datos  
 En esta sección se describe cómo crear la canalización de flujo de datos que procesa los elementos de trabajo y actualiza las barras de progreso.  
  
#### <a name="to-create-the-dataflow-pipeline"></a>Para crear la canalización de flujo de datos  
  
1.  En el proyecto, agregue una referencia a System.Threading.Tasks.Dataflow.dll.  
  
2.  Asegúrese de que Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contenga las siguientes instrucciones `using` (`Imports` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Agregue la clase `WorkItem` como un tipo interno de la clase `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Agregue a la clase `Form1` los miembros de datos siguientes:  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Agregue el método siguiente, `CreatePipeline`, a la clase `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Dado que los bloques de flujo de datos `incrementProgress` y `decrementProgress` actúan sobre la interfaz de usuario, es importante que esta acción se produzca en el subproceso de interfaz de usuario. Para lograr esto, opción durante la construcción de estos objetos cada uno de ellos proporcionan un <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> objeto que tiene el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> propiedad establecida en <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. El método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> crea un objeto <xref:System.Threading.Tasks.TaskScheduler> que funciona en el contexto de sincronización actual. Dado que al constructor `Form1` se le llama desde el subproceso de interfaz de usuario, las acciones de los bloques de flujo de datos `incrementProgress` y `decrementProgress` se ejecutan también en el subproceso de interfaz de usuario.  
  
 Este ejemplo se establece la <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad cuando construye los miembros de la canalización. Dado que el <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> propiedad permanentemente cancela la ejecución de bloques de flujo de datos, debe volver a crearse la canalización completa cuando el usuario cancela la operación y, a continuación, desea agregar más elementos de trabajo a la canalización. Para consultar un ejemplo en el que se muestre una forma alternativa de cancelar un bloque de flujo de datos, a fin de que se pueda realizar otro trabajo después de cancelar una operación, vea [Tutorial: uso de flujo de datos en una Aplicación de Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a>Conexión de la canalización de flujo de datos a la interfaz de usuario  
 En esta sección se describe cómo conectar la canalización de flujo de datos a la interfaz de usuario. Tanto la creación de la canalización como la adición de elementos de trabajo a la canalización se controlan mediante el controlador de eventos para el botón **Agregar elementos de trabajo**. La cancelación se inicia con el botón **Cancelar**. Cuando el usuario hace clic en cualquiera de estos botones, se inicia la acción correspondiente de forma asincrónica.  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a>Para conectar la canalización de flujo de datos a la interfaz de usuario  
  
1.  En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **agregar elementos de trabajo** botón.  
  
2.  Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> eventos para el **agregar elementos de trabajo** botón.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  En el Diseñador de formularios del formulario principal, cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para el **cancelar** botón.  
  
4.  Implemente el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para el **cancelar** botón.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, se muestra el código completo de Form1.cs (Form1.vb con [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 En la ilustración siguiente se muestra la aplicación en ejecución.  
  
 ![Aplicación de Windows Forms](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")  
  
## <a name="robust-programming"></a>Programación sólida  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
