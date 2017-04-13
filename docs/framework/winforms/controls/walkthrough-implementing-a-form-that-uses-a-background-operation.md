---
title: "Tutorial: Implementar un formulario que utiliza una operaci&#243;n en segundo plano | Microsoft Docs"
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
  - "BackgroundWorker (componente)"
  - "formularios, operaciones en segundo plano"
  - "formularios, multithreading"
  - "subprocesamiento [Windows Forms], operaciones en segundo plano"
  - "subprocesamiento [Windows Forms], formularios"
  - "subprocesamiento [Windows Forms], tutoriales"
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Tutorial: Implementar un formulario que utiliza una operaci&#243;n en segundo plano
Si tiene una operación que puede tardar mucho tiempo en completarse y no desea que la interfaz de usuario deje de responder, utilice la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.  
  
 Este tutorial muestra cómo utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para realizar operaciones "en segundo plano" que tardan mucho tiempo, mientras la interfaz de usuario permanece receptiva.  Cuando haya terminado, tendrá una aplicación que calcula de forma asincrónica series de Fibonacci.  Aunque el cálculo de series de Fibonacci muy grandes puede tardar una considerable cantidad de tiempo, el subproceso principal de la interfaz de usuario no se interrumpirá por este retraso, y el formulario seguirá receptivo durante la operación.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear una aplicación basada en Windows  
  
-   Crear un <xref:System.ComponentModel.BackgroundWorker> en el formulario  
  
-   Agregar los controladores de eventos asincrónicos  
  
-   Agregar la información del progreso y la admisión de la cancelación  
  
 Para una lista completa del código utilizado en este ejemplo, vea [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear un formulario que utiliza una operación en segundo plano  
  
1.  Cree un proyecto de aplicación basada en Windows denominado `BackgroundWorkerExample`.  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Form1** y elija **Cambiar nombre** en el menú contextual.  Cambie el nombre de archivo `FibonacciCalculator`.  Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código '`Form1`'.  
  
3.  Arrastre un <xref:System.Windows.Forms.NumericUpDown> desde el **Cuadro de herramientas** al formulario.  Establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> en `1` y la propiedad <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> en `91`.  
  
4.  Agregue dos controles <xref:System.Windows.Forms.Button> al formulario.  
  
5.  Cambie el nombre del primer `startAsyncButton` del control <xref:System.Windows.Forms.Button> y establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en `Start Async`.  Cambie el nombre del segundo `cancelAsyncButton` del control <xref:System.Windows.Forms.Button> y establezca la propiedad <xref:System.Windows.Forms.Control.Text%2A> en `Cancel Async`.  Establezca la propiedad <xref:System.Windows.Forms.Control.Enabled%2A> en `false`.  
  
6.  Cree un controlador de eventos para ambos eventos <xref:System.Windows.Forms.Control.Click> de los controles <xref:System.Windows.Forms.Button>.  Para obtener información detallada, vea [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/es-es/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Arrastre un <xref:System.Windows.Forms.Label> desde el **Cuadro de herramientas** al formulario y cambie el nombre a `resultLabel`.  
  
8.  Arrastre un <xref:System.Windows.Forms.ProgressBar> desde el **Cuadro de herramientas** al formulario.  
  
## Crear un control BackgroundWorker en el formulario  
 Puede crear un <xref:System.ComponentModel.BackgroundWorker> para la operación asincrónica mediante el **Diseñador de** **Windows Forms**.  
  
#### Para crear un control BackgroundWorker con el diseñador  
  
-   En la ficha **Componentes** del **Cuadro de herramientas**, arrastre un componente <xref:System.ComponentModel.BackgroundWorker> al formulario.  
  
## Agregar los controladores de eventos asincrónicos  
 Ahora ya se pueden agregar los controladores de eventos para los eventos asincrónicos del componente <xref:System.ComponentModel.BackgroundWorker>.  Uno de estos controladores de eventos llama a la operación que lleva mucho tiempo y que se ejecutará en segundo plano, que calcula la serie de Fibonacci.  
  
#### Para implementar los controladores de eventos asincrónicos  
  
1.  En la ventana **Propiedades**, con el componente <xref:System.ComponentModel.BackgroundWorker> aún seleccionado, haga clic en el botón **Eventos**.  Haga doble clic en los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> para crear los controladores de eventos.  Para obtener más información acerca de cómo utilizar controladores de eventos, vea [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/es-es/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Cree un nuevo método, denominado `ComputeFibonacci`, en el formulario.  Este método hace el trabajo real y se ejecutará en segundo plano.  Este código muestra la implementación recursiva del algoritmo de Fibonacci, notablemente ineficaz, que lleva exponencialmente mucho más tiempo para finalizar los números más grandes.  Se utiliza aquí con fines ilustrativos, para mostrar una operación que puede introducir grandes retrasos en la aplicación.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  En el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>, agregue una llamada al método `ComputeFibonacci`.  Tome el primer parámetro para `ComputeFibonacci` desde la propiedad <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> de <xref:System.ComponentModel.DoWorkEventArgs>.  Los parámetros <xref:System.ComponentModel.BackgroundWorker> y <xref:System.ComponentModel.DoWorkEventArgs> se utilizarán después para la información del progreso y para admitir la cancelación.  Asigne el valor devuelto de `ComputeFibonacci` a la propiedad <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> del objeto <xref:System.ComponentModel.DoWorkEventArgs>.  Este resultado estará disponible para el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
    > [!NOTE]
    >  El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> no hace referencia directamente a la variable de la instancia `backgroundWorker1`, ya que de este modo se uniría este controlador de eventos a una instancia específica de <xref:System.ComponentModel.BackgroundWorker>.  En su lugar, se recupera del parámetro `sender` una referencia al control <xref:System.ComponentModel.BackgroundWorker> que provocó este evento.  Esto es importante cuando el formulario hospede más de un <xref:System.ComponentModel.BackgroundWorker>.  Es también importante no manipular ningún objeto de la interfaz de usuario en el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>.  En su lugar, comuníquese con la interfaz de usuario a través de los eventos <xref:System.ComponentModel.BackgroundWorker>.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  En el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control `startAsyncButton`, agregue el código que inicia la operación asincrónica.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  En el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, asigne el resultado del cálculo al control `resultLabel`.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## Agregar la información del progreso y la admisión de la cancelación  
 Para aquellas operaciones asincrónicas que tardan mucho tiempo, suele ser deseable informar del progreso al usuario y permitir que éste cancele la operación.  La clase <xref:System.ComponentModel.BackgroundWorker> proporciona un evento que le permite enviar el progreso a medida que se realiza la operación en segundo plano.  También proporciona un marcador que permite a su código de trabajo detectar una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> e interrumpirse.  
  
#### Para implementar la información de progreso  
  
1.  En la ventana **Propiedades**, seleccione la propiedad `backgroundWorker1`.  Establezca las propiedades <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en `true`.  
  
2.  Declare dos variables en el formulario `FibonacciCalculator`.  Éstas se utilizarán para realizar el seguimiento del progreso.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Agregue un controlador de eventos para el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  En el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, actualice <xref:System.Windows.Forms.ProgressBar> con la propiedad <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> del parámetro <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### Para implementar la admisión de la cancelación  
  
1.  En el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control `cancelAsyncButton`, agregue el código que cancela la operación asincrónica.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  Los fragmentos de código siguientes del método `ComputeFibonacci` informan del progreso y admiten la cancelación.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## Punto de control  
 Llegado este punto, puede generar y ejecutar la aplicación Fibonacci Calculator.  
  
#### Para probar el proyecto  
  
-   Presione F5 para compilar y ejecutar la aplicación.  
  
     Mientras la operación se está ejecutando en segundo plano, verá que <xref:System.Windows.Forms.ProgressBar> muestra el progreso del cálculo hacia su finalización.  También puede cancelar la operación pendiente.  
  
     En el caso de números pequeños, el cálculo debería ser muy rápido, pero con los números más grandes, debería ver un considerable retraso.  Si ha especificado un valor de 30 o superior, debería ver un retraso de varios segundos, dependiendo de la velocidad de su equipo.  Para los valores mayores de 40, puede tardar minutos u horas finalizar el cálculo.  Mientras la calculadora está ocupada calculando una serie de Fibonacci grande, observe que se puede mover libremente por todo el formulario, minimizarlo, maximizarlo e incluso descartarlo.  Esto es debido a que el subproceso principal de la interfaz de usuario no está esperando a que finalice el cálculo.  
  
## Pasos siguientes  
 Ahora que ha implementado un formulario que utiliza un componente <xref:System.ComponentModel.BackgroundWorker> para ejecutar un cálculo en segundo plano, puede explorar otras posibilidades para las operaciones asincrónicas:  
  
-   Utilice varios objetos <xref:System.ComponentModel.BackgroundWorker> para distintas operaciones simultáneas.  
  
-   Para depurar su aplicación multiproceso, vea [Cómo: Utilizar la ventana Subprocesos](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
-   Implemente su propio componente que admita el modelo de programación asincrónica.  Para obtener más información, vea [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
    > [!CAUTION]
    >  Al utilizar multithreading de cualquier tipo, se expone potencialmente a errores muy graves y complejos.  Consulte [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.  
  
## Vea también  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/es-es/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Tutorial: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)   
 [BackgroundWorker \(Componente\)](../../../../docs/framework/winforms/controls/backgroundworker-component.md)