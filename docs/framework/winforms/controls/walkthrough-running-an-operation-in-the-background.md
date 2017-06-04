---
title: "Tutorial: Ejecutar una operaci&#243;n en segundo plano | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "operaciones en segundo plano"
  - "tareas en segundo plano"
  - "subprocesos en segundo plano"
  - "BackgroundWorker (clase), ejemplos"
  - "formularios, operaciones en segundo plano"
  - "formularios, multithreading"
  - "subprocesamiento [Windows Forms], operaciones en segundo plano"
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Tutorial: Ejecutar una operaci&#243;n en segundo plano
Si tiene una operación que llevará mucho tiempo completarse y no desea que provoque demoras en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.  
  
 Para obtener una lista completa del código utilizado en este ejemplo, vea [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para ejecutar en segundo plano una operación  
  
1.  Con el formulario activo en el Diseñador de Windows Forms, arrastre dos controles <xref:System.Windows.Forms.Button> del **Cuadro de herramientas** al formulario y después establezca las propiedades `Name` y <xref:System.Windows.Forms.Control.Text%2A> de los botones de acuerdo con la tabla siguiente.  
  
    |Button|Name|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|Iniciar|  
    |`button2`|`cancelBtn`|Cancelar|  
  
2.  Abra el **Cuadro de herramientas**, haga clic en la ficha **Componentes** y, a continuación, arrastre el componente <xref:System.ComponentModel.BackgroundWorker> al formulario.  
  
     Aparecerá el componente `backgroundWorker1` en la **Bandeja de componentes**.  
  
3.  En la ventana **Propiedades**, establezca la propiedad <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en `true`.  
  
4.  En la ventana **Propiedades**, haga clic en el botón **Eventos** y, a continuación, haga doble clic en los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> para crear los controladores de eventos.  
  
5.  Inserte el código que lleva mucho tiempo en el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
6.  Extraiga los parámetros necesarios para la operación de la propiedad <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> del parámetro <xref:System.ComponentModel.DoWorkEventArgs>.  
  
7.  Asigne el resultado del cálculo a la propiedad <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> de <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Éste estará disponible al controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Inserte el código para recuperar el resultado de la operación en el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Implemente el método `TimeConsumingOperation`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. En el Diseñador de Windows Forms, haga doble clic en `startButton` para crear el controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
11. Llame al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> en el controlador de eventos <xref:System.Windows.Forms.Control.Click> para `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. En el Diseñador de Windows Forms, haga doble clic en `cancelButton` para crear el controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
13. Llame al método <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> en el controlador de eventos <xref:System.Windows.Forms.Control.Click> para `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. En la parte superior del archivo, importe los espacios de nombres System.ComponentModel y System.Threading.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Presione F6 para compilar la solución y, a continuación, presione CTRL\-F5 para ejecutar la aplicación fuera del depurador.  
  
> [!NOTE]
>  Si presiona F5 para ejecutar la aplicación bajo el depurador, éste detectará y mostrará la excepción generada en el método `TimeConsumingOperation`.  Cuando ejecuta la aplicación fuera del depurador, <xref:System.ComponentModel.BackgroundWorker> controla la excepción y la almacena en memoria caché en la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> de <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Haga clic en el botón **Iniciar** para ejecutar una operación asincrónica y, a continuación, haga clic en el botón **Cancelar** para detener una operación asincrónica en ejecución.  
  
     El resultado de cada operación se muestra en <xref:System.Windows.Forms.MessageBox>.  
  
## Pasos siguientes  
  
-   Implemente un formulario que informa del progreso a medida que prosigue la operación asincrónica.  Para obtener más información, vea [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Implemente una clase que admite el Modelo asincrónico para componentes.  Para obtener más información, vea [Implementing the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## Vea también  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [BackgroundWorker \(Componente\)](../../../../docs/framework/winforms/controls/backgroundworker-component.md)