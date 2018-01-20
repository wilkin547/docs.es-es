---
title: "Tutorial: Ejecutar una operación en segundo plano"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca0892e9d384eefb0fec87a7717222fefb779d12
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Tutorial: Ejecutar una operación en segundo plano
Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.  
  
 Para obtener una lista completa del código utilizado en este ejemplo, vea [Cómo: ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-run-an-operation-in-the-background"></a>Para ejecutar una operación en segundo plano  
  
1.  Con el formulario activo en el Diseñador de Windows Forms, arrastre dos <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** al formulario y, a continuación, establezca el `Name` y <xref:System.Windows.Forms.Control.Text%2A> propiedades de los botones de acuerdo con la tabla siguiente.  
  
    |Botón|nombre|Texto|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Start**|  
    |`button2`|`cancelBtn`|**Cancelar**|  
  
2.  Abra la **cuadro de herramientas**, haga clic en el **componentes** ficha y, a continuación, arrastre el <xref:System.ComponentModel.BackgroundWorker> componente al formulario.  
  
     El `backgroundWorker1` componente aparecerá en el **Bandeja de componentes**.  
  
3.  En el **propiedades** ventana, establezca el <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> propiedad `true`.  
  
4.  En el **propiedades** ventana, haga clic en el **eventos** botón y, a continuación, haga doble clic en el <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventos para crear controladores de eventos.  
  
5.  Inserte el código que consumen muchos recursos en el <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos.  
  
6.  Extraer todos los parámetros requeridos por la operación de la <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs> parámetro.  
  
7.  Asignar el resultado del cálculo para la <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Esta forma se estén disponibles para el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Inserte código para recuperar el resultado de la operación en el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Implemente el método `TimeConsumingOperation`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. En el Diseñador de Windows Forms, haga doble clic en `startButton` para crear el <xref:System.Windows.Forms.Control.Click> controlador de eventos.  
  
11. Llame a la <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> método en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. En el Diseñador de Windows Forms, haga doble clic en `cancelButton` para crear el <xref:System.Windows.Forms.Control.Click> controlador de eventos.  
  
13. Llame a la <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> método en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. En la parte superior del archivo, importe los espacios de nombres System.ComponentModel y System.Threading.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Presione F6 para compilar la solución y, a continuación, presione CTRL-F5 para ejecutar la aplicación fuera del depurador.  
  
> [!NOTE]
>  Si presiona F5 para ejecutar la aplicación en el depurador, la excepción se produce en el `TimeConsumingOperation` método es detectado y mostrado por el depurador. Al ejecutar la aplicación fuera del depurador, el <xref:System.ComponentModel.BackgroundWorker> controla la excepción y lo almacena en caché en el <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> propiedad de la <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Haga clic en el **iniciar** para ejecutar una operación asincrónica y, a continuación, haga clic en el **cancelar** botón para detener una operación asincrónica en ejecución.  
  
     El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.  
  
## <a name="next-steps"></a>Pasos siguientes  
  
-   Implementar un formulario que informa del progreso mientras se realiza una operación asincrónica. Para obtener más información, consulte [Cómo: implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Implementar una clase que admita el modelo asincrónico para componentes. Para obtener más información, consulte [implementar el modelo asincrónico basado en eventos](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
