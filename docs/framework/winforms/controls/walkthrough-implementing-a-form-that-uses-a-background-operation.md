---
title: "Tutorial: Implementar un formulario que utiliza una operación en segundo plano"
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
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89a352baed4d07c3c935643e9962131a20af2802
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a>Tutorial: Implementar un formulario que utiliza una operación en segundo plano
Si tiene una operación que tarda mucho tiempo en completarse, y no desea que la interfaz de usuario (UI) deje de responder o "bloqueo", puede usar el <xref:System.ComponentModel.BackgroundWorker> clase para ejecutar la operación en otro subproceso.  
  
 Este tutorial muestra cómo utilizar la <xref:System.ComponentModel.BackgroundWorker> clase para realizar cálculos que consumen muchos recursos "en"segundo plano, mientras que la interfaz de usuario sigue respondiendo.  Cuando haya terminado, tendrá una aplicación que calcula de forma asincrónica los números de Fibonacci. Aunque se puede tardar un tiempo considerable en calcular un número de Fibonacci elevado, el subproceso de interfaz de usuario principal no se interrumpirá por este retraso, y el formulario seguirá respondiendo durante el cálculo.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear una aplicación basada en Windows  
  
-   Crear un <xref:System.ComponentModel.BackgroundWorker> en el formulario  
  
-   Agregar controladores de eventos asincrónicos  
  
-   Agregar informes de progreso y compatibilidad con la cancelación  
  
 Para ver una lista completa del código utilizado en este ejemplo, consulte [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-a-form-that-uses-a-background-operation"></a>Para crear un formulario que utilice una operación en segundo plano  
  
1.  Cree un proyecto de aplicación basada en Windows llamado `BackgroundWorkerExample`. Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1** y seleccione **Cambiar nombre** en el menú contextual. Cambie el nombre del archivo a `FibonacciCalculator`. Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "`Form1`".  
  
3.  Arrastre un <xref:System.Windows.Forms.NumericUpDown> controlar desde la **cuadro de herramientas** hasta el formulario. Establecer el <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> propiedad `1` y <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> propiedad a `91`.  
  
4.  Agregar dos <xref:System.Windows.Forms.Button> controles al formulario.  
  
5.  Cambiar el nombre de la primera <xref:System.Windows.Forms.Button> control `startAsyncButton` y establezca el <xref:System.Windows.Forms.Control.Text%2A> propiedad `Start Async`. Cambiar el nombre de la segunda <xref:System.Windows.Forms.Button> control `cancelAsyncButton`y establezca el <xref:System.Windows.Forms.Control.Text%2A> propiedad `Cancel Async`. Establecer su <xref:System.Windows.Forms.Control.Enabled%2A> propiedad `false`.  
  
6.  Crear un controlador de eventos de ambos el <xref:System.Windows.Forms.Button> controles <xref:System.Windows.Forms.Control.Click> eventos. Para ver detalles, consulte [Cómo: Crear controladores de eventos mediante el diseñador](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** hasta el formulario y cambie su nombre `resultLabel`.  
  
8.  Arrastre un <xref:System.Windows.Forms.ProgressBar> controlar desde la **cuadro de herramientas** hasta el formulario.  
  
## <a name="creating-a-backgroundworker-in-your-form"></a>Crear un componente BackgroundWorker en el formulario  
 Puede crear el <xref:System.ComponentModel.BackgroundWorker> para la operación asincrónica con el **Windows** **Diseñador de formularios**.  
  
#### <a name="to-create-a-backgroundworker-with-the-designer"></a>Para crear un componente BackgroundWorker con el diseñador  
  
-   Desde el **componentes** pestaña de la **cuadro de herramientas**, arrastre un <xref:System.ComponentModel.BackgroundWorker> al formulario.  
  
## <a name="adding-asynchronous-event-handlers"></a>Agregar controladores de eventos asincrónicos  
 Ahora está listo para agregar controladores de eventos para el <xref:System.ComponentModel.BackgroundWorker> eventos asincrónicos del componente. Se llama a la laboriosa operación que se ejecutará en segundo plano, que calcula los números de Fibonacci, mediante uno de estos controladores de eventos.  
  
#### <a name="to-implement-asynchronous-event-handlers"></a>Para implementar controladores de eventos asincrónicos  
  
1.  En el **propiedades** ventana, con el <xref:System.ComponentModel.BackgroundWorker> componente aún seleccionado, haga clic en el **eventos** botón. Haga doble clic en el <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventos para crear controladores de eventos. Para más información sobre cómo utilizar controladores de eventos, consulte [Cómo: Crear controladores de eventos mediante el diseñador](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Cree un método llamado `ComputeFibonacci` en el formulario. Este método realiza el trabajo en sí y se ejecutará en segundo plano. Este código muestra la implementación recursiva del algoritmo de Fibonacci, que es notablemente ineficaz y tarda exponencialmente más tiempo en completarse para los números más elevados. Se usa aquí a modo de ilustración, para mostrar una operación que puede suponer grandes retrasos en su aplicación.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  En el <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos, agregue una llamada a la `ComputeFibonacci` método. Tome el primer parámetro `ComputeFibonacci` desde el <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs>. El <xref:System.ComponentModel.BackgroundWorker> y <xref:System.ComponentModel.DoWorkEventArgs> parámetros se usará más adelante para informes de progreso y la cancelación admite. Asignar el valor devuelto de `ComputeFibonacci` a la <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs>. Este resultado estará disponible para el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos.  
  
    > [!NOTE]
    >  El <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos no hace referencia la `backgroundWorker1` instancia variable directamente, este modo se uniría este controlador de eventos a una instancia específica de <xref:System.ComponentModel.BackgroundWorker>. En su lugar, una referencia a la <xref:System.ComponentModel.BackgroundWorker> que genera este evento se recupera desde la `sender` parámetro. Esto es importante cuando el formulario aloje más de un <xref:System.ComponentModel.BackgroundWorker>. También es importante no manipular los objetos de interfaz de usuario en su <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos. En su lugar, se comunican con la interfaz de usuario a través de la <xref:System.ComponentModel.BackgroundWorker> eventos.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  En el `startAsyncButton` del control <xref:System.Windows.Forms.Control.Click> controlador de eventos, agregue el código que inicia la operación asincrónica.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  En el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos, asigne el resultado del cálculo para el `resultLabel` control.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## <a name="adding-progress-reporting-and-support-for-cancellation"></a>Agregar informes de progreso y compatibilidad con la cancelación  
 Para las operaciones asincrónicas que vayan a tardar mucho tiempo, suele ser deseable informar sobre el progreso al usuario y permitir que cancele la operación. La <xref:System.ComponentModel.BackgroundWorker> clase proporciona un evento que le permite registrar el progreso como su continúa de la operación de fondo. También proporciona una marca que permite que el código de trabajo detectar una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> e interrumpir a sí mismo.  
  
#### <a name="to-implement-progress-reporting"></a>Para implementar los informes de progreso  
  
1.  En la ventana **Propiedades**, seleccione `backgroundWorker1`. Establezca las propiedades <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en `true`.  
  
2.  Declare dos variables en el formulario `FibonacciCalculator`. Se utilizarán para realizar un seguimiento del progreso.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Agregue un controlador de eventos para el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>. En el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> controlador de eventos, actualice la <xref:System.Windows.Forms.ProgressBar> con el <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> propiedad de la <xref:System.ComponentModel.ProgressChangedEventArgs> parámetro.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### <a name="to-implement-support-for-cancellation"></a>Para implementar la compatibilidad con la cancelación  
  
1.  En el `cancelAsyncButton` del control <xref:System.Windows.Forms.Control.Click> controlador de eventos, agregue el código que cancela la operación asincrónica.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  Los siguientes fragmentos de código en el método `ComputeFibonacci` informan sobre el progreso y son compatibles con la cancelación.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este punto, puede compilar y ejecutar la aplicación de calculadora de Fibonacci.  
  
#### <a name="to-test-your-project"></a>Para probar el proyecto  
  
-   Presione F5 para compilar y ejecutar la aplicación.  
  
     Mientras el cálculo se ejecuta en segundo plano, verá el <xref:System.Windows.Forms.ProgressBar> mostrar el progreso del cálculo hacia su finalización. También puede cancelar la operación pendiente.  
  
     Para los números pequeños, el cálculo debería ser muy rápido pero, para los números mayores, debería darse un retraso notable. Si escribe un valor de 30 o superior, debería ver un retraso de varios segundos, dependiendo de la velocidad del equipo. Para los valores superiores a 40, se pueden tardar minutos u horas en finalizar el cálculo. Mientras la calculadora está ocupada calculando un número de Fibonacci elevado, observe que tiene libertad para mover el formulario, minimizarlo, maximizarlo e incluso descartarlo. Esto se debe a que el subproceso de interfaz de usuario principal no está esperando a que finalice el cálculo.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha implementado un formulario que utiliza un <xref:System.ComponentModel.BackgroundWorker> componente para ejecutar un cálculo en segundo plano, puede explorar otras posibilidades para las operaciones asincrónicas:  
  
-   Usar varios <xref:System.ComponentModel.BackgroundWorker> objetos para varias operaciones simultáneas.  
  
-   Para depurar su aplicación multiproceso, consulte [Cómo: Utilizar la ventana Subprocesos](/visualstudio/debugger/how-to-use-the-threads-window).  
  
-   Implemente su propio componente que admita el modelo de programación asincrónica. Para más información, consulte [Event-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Introducción al patrón asincrónico basado en eventos).  
  
    > [!CAUTION]
    >  Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos. Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Procedimientos recomendados para el subprocesamiento administrado](../../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Subprocesamiento múltiple en componentes](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [NO está en la compilación: Multithreading en Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Tutorial: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 [Componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
