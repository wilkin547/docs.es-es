---
title: 'Cómo: Especificar un programador de tareas en un bloque de flujos de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, linking to task scheduler in TPL
- Task Parallel Library, dataflows
- task scheduler, linking from TPL
ms.assetid: 27ece374-ed5b-49ef-9cec-b20db34a65e8
ms.openlocfilehash: 76c9e75f787c28657af143b46bb22d08039e2dc4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288139"
---
# <a name="how-to-specify-a-task-scheduler-in-a-dataflow-block"></a>Cómo: Especificar un programador de tareas en un bloque de flujos de datos
Este documento muestra cómo asociar un programador de tareas específico al usar un flujo de datos en la aplicación. En el ejemplo, se usa la clase <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> en una aplicación de Windows Forms para mostrar cuándo están activas las tareas de lectura y cuándo está activa una tarea de escritura. También se usa el método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> para permitir que un bloque de flujo de datos se ejecute en el subproceso de la interfaz de usuario.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="to-create-the-windows-forms-application"></a>Para crear la aplicación de Windows Forms  
  
1. Cree un proyecto **Aplicación de Windows Forms** de Visual C# o Visual Basic. En los pasos siguientes, el proyecto se denomina `WriterReadersWinForms`.  
  
2. En el diseñador de formularios del formulario principal, Form1.cs (Form1.vb para Visual Basic), agregue cuatro controles <xref:System.Windows.Forms.CheckBox>. Establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> como **Lector 1** para `checkBox1`, **Lector 2** para `checkBox2`, **Lector 3** para `checkBox3` y **Escritor** para `checkBox4`. Establezca la propiedad <xref:System.Windows.Forms.Control.Enabled%2A> de cada control como `False`.  
  
3. Agregue un control <xref:System.Windows.Forms.Timer> al formulario. Establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> en `2500`.  
  
## <a name="adding-dataflow-functionality"></a>Agregar funcionalidad de flujo de datos  
 En esta sección, se describe cómo crear los bloques de flujo de datos que participan en la aplicación y cómo asociar cada uno a un programador de tareas.  
  
### <a name="to-add-dataflow-functionality-to-the-application"></a>Para agregar funcionalidad de flujo de datos a la aplicación  
  
1. En el proyecto, agregue una referencia a System.Threading.Tasks.Dataflow.dll.  
  
2. Asegúrese de que Form1.cs (Form1.vb para Visual Basic) contenga las siguientes instrucciones `using` (`Imports` en Visual Basic).  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#1)]  
  
3. Agregue un miembro de datos <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> a la clase `Form1`.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#2)]  
  
4. En el constructor `Form1`, después de llamar a `InitializeComponent`, cree un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> que alterne el estado de los objetos <xref:System.Windows.Forms.CheckBox>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#3)]  
  
5. En el constructor `Form1`, cree un objeto <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> y cuatro objetos <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> para cada objeto <xref:System.Windows.Forms.CheckBox>. Para cada objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, especifique un objeto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> que tenga la propiedad <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> establecida como la propiedad <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> para los lectores, y como la propiedad <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> para el escritor.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#4)]  
  
6. En el constructor `Form1`, inicie el objeto <xref:System.Windows.Forms.Timer>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#5)]  
  
7. En el diseñador de formularios del formulario principal, cree un controlador de eventos para el evento <xref:System.Windows.Forms.Timer.Tick> del temporizador.  
  
8. Implemente el evento <xref:System.Windows.Forms.Timer.Tick> del temporizador.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#6)]  
  
 Dado que el bloque de flujo de datos `toggleCheckBox` actúa en la interfaz de usuario, es importante que esta acción se produzca en el subproceso de la interfaz de usuario. Para lograrlo, durante la construcción, este objeto proporciona un objeto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> que tiene la propiedad <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> establecida como <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. El método <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> crea un objeto <xref:System.Threading.Tasks.TaskScheduler> que funciona en el contexto de sincronización actual. Dado que al constructor `Form1` se le llama desde el subproceso de la interfaz de usuario, la acción del bloque de flujo de datos `toggleCheckBox` se ejecuta también en el subproceso de la interfaz de usuario.  
  
 En este ejemplo, también se usa la clase <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> para permitir que algunos bloques de flujo de datos actúen de forma simultánea y que otro bloque de flujo de datos actúe de forma exclusiva con respecto a todos los demás bloques de flujo de datos que se ejecutan en el mismo objeto <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair>. Esta técnica es útil cuando varios bloques de flujo de datos comparten un recurso y algunos requieren acceso exclusivo a ese recurso, ya que evita la necesidad de sincronizar manualmente el acceso a ese recurso. Al eliminar la sincronización manual, se puede hacer que el código sea más eficiente.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra el código completo de Form1.cs (Form1.vb para Visual Basic).  
  
 [!code-csharp[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#100)]  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
