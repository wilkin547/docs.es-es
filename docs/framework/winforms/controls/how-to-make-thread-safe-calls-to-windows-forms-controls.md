---
title: "C&#243;mo: Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHInvalidOperation.WinForms.IllegalCrossThreadCall"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "seguridad para subprocesos, llamar a controles [Windows Forms]"
  - "llamar a controles, seguridad para subprocesos [Windows Forms]"
  - "CheckForIllegalCrossThreadCalls (propiedad) [Windows Forms]"
  - "controles de Windows Forms, multithreading"
  - "clase BackgroundWorker, ejemplos"
  - "subprocesamiento [Windows Forms], llamadas a través de subprocesos"
  - "controles [Windows Forms], multithreading"
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms
Si utiliza multithreading para mejorar el rendimiento de las aplicaciones de Windows Forms, asegúrese de que realiza llamadas a los controles de una manera segura para subprocesos.  
  
 El acceso a los controles de Windows Forms no es intrínsecamente seguro para subprocesos. Si tiene dos o más subprocesos que manipulan el estado de un control, es posible que este acabe teniendo un estado incoherente. También pueden producirse otros errores relacionados con los subprocesos, como interbloqueos y condiciones de carrera. Es importante asegurarse de que el acceso a los controles se realiza de una manera segura para los subprocesos.  
  
 No es seguro llamar a un control desde un subproceso distinto del que creó el control sin utilizar el método <xref:System.Windows.Forms.Control.Invoke%2A>. El siguiente es un ejemplo de una llamada que no es segura para subprocesos.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#6)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#6)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#6)]  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ayuda a detectar si el acceso a los controles se realiza de un modo no seguro para subprocesos. Cuando se ejecuta la aplicación en el depurador y un subproceso distinto del que creó un control intenta llamar a ese control, el depurador genera una excepción <xref:System.InvalidOperationException> con el siguiente mensaje: “Se tuvo acceso al control *nombre de control* desde un subproceso distinto a aquel en que lo creó”.  
  
 Esta excepción aparece durante la depuración y, en algunas circunstancias, en tiempo de ejecución. Esta excepción también puede verse al depurar aplicaciones que se escribieron con un [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] anterior a [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Le rogamos que corrija este problema cuando lo vea, pero puede desactivarlo si establece la propiedad <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> en `false`. Esto hace que el control se ejecute como si lo hiciera en Visual Studio .NET 2003 y [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)].  
  
> [!NOTE]
>  Si utiliza controles ActiveX en un formulario, puede aparecer la excepción <xref:System.InvalidOperationException> entre subprocesos cuando se ejecuta en el depurador. Cuando esto ocurre, el control ActiveX no admite multithreading. Para obtener más información sobre el uso de controles ActiveX con Windows Forms, consulte [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md). Si está usando Visual Studio, puede evitar esta excepción si deshabilita el proceso de hospedaje de Visual Studio; consulte [Cómo: Deshabilitar el proceso de alojamiento](../Topic/How%20to:%20Disable%20the%20Hosting%20Process.md).  
  
## Llamadas seguras para subprocesos a controles de Windows Forms  
  
#### Para realizar una llamada segura para subprocesos a un control de Windows Forms  
  
1.  Consulte la propiedad <xref:System.Windows.Forms.Control.InvokeRequired%2A> del control.  
  
2.  Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `true`, llame a <xref:System.Windows.Forms.Control.Invoke%2A> con un delegado que realice la llamada real al control.  
  
3.  Si <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `false`, llame directamente al control.  
  
 En el ejemplo de código siguiente se implementa una llamada segura para subprocesos en el método `ThreadProcSafe`, que se ejecuta en el subproceso en segundo plano. Si el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.InvokeRequired%2A> devuelve `true`, el método `ThreadProcSafe` crea una instancia de `SetTextCallback` y la pasa al método <xref:System.Windows.Forms.Control.Invoke%2A> del formulario. Esto hace que el método `SetText` se llame en el subproceso que creó el control <xref:System.Windows.Forms.TextBox> \(control\) y en el contexto de este subproceso la propiedad <xref:System.Windows.Forms.Control.Text%2A> se establece directamente.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#7)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#7)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#3)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#8)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#8)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#8)]  
  
## Llamadas seguras para subprocesos mediante BackgroundWorker  
 La mejor manera de implementar el multithreading en la aplicación consiste en utilizar el componente <xref:System.ComponentModel.BackgroundWorker>. El componente <xref:System.ComponentModel.BackgroundWorker> utiliza un modelo orientado a eventos para multithreading. El subproceso en segundo plano se encarga de la ejecución del controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y el subproceso que crea los controles se encarga de la ejecución de los controladores de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>. Puede llamar a los controles desde los controladores de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
#### Para realizar llamadas seguras para subprocesos mediante BackgroundWorker  
  
1.  Cree un método para realizar el trabajo deseado en el subproceso en segundo plano. No llame a los controles creados por el subproceso principal en este método.  
  
2.  Cree un método para informar de los resultados del trabajo en segundo plano una vez que este finalice. Puede llamar a los controles creados por el subproceso principal en este método.  
  
3.  Enlace el método creado en el paso 1 al evento <xref:System.ComponentModel.BackgroundWorker.DoWork> de una instancia de <xref:System.ComponentModel.BackgroundWorker>, y enlace el método creado en el paso 2 al evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> de la misma instancia.  
  
4.  Para iniciar el subproceso en segundo plano, llame al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> de la instancia <xref:System.ComponentModel.BackgroundWorker>.  
  
 En el ejemplo de código siguiente, el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> utiliza <xref:System.Threading.Thread.Sleep%2A> para simular un trabajo que tarda algún tiempo. No llama al control <xref:System.Windows.Forms.TextBox> del formulario. La propiedad <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.Text%2A> se establece directamente en el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#5)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#5)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#5)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#9)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#9)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#9)]  
  
 También puede notificar el progreso de una tarea en segundo plano mediante el uso del evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>. Para obtener un ejemplo que incluye ese evento, consulte <xref:System.ComponentModel.BackgroundWorker>.  
  
## Ejemplo  
 El siguiente ejemplo de código es una aplicación de Windows Forms completa que consta de un formulario con tres botones y un cuadro de texto. El primer botón muestra el acceso no seguro entre subprocesos, el segundo botón muestra el acceso seguro mediante el uso de <xref:System.Windows.Forms.Control.Invoke%2A> y el tercer botón muestra el acceso seguro mediante el uso de <xref:System.ComponentModel.BackgroundWorker>.  
  
> [!NOTE]
>  Para obtener instrucciones sobre cómo ejecutar el ejemplo, consulte [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/es-es/cc447f7e-4c3b-4397-9d05-aeba3ca49416). Este ejemplo requiere referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#1)]  
  
 Al ejecutar la aplicación y hacer clic en el botón **Unsafe Call**, inmediatamente se ve “Escrito por el subproceso principal” en el cuadro de texto. Dos segundos después, cuando se intenta realizar la llamada no segura, el depurador de Visual Studio indica que se ha producido una excepción. El depurador se detiene en la línea del subproceso en segundo plano que intentó escribir directamente en el cuadro de texto. Para probar los otros dos botones, tendrá que reiniciar la aplicación. Al hacer clic en el botón **Safe Call**, en el cuadro de texto aparece “Escrito por el subproceso principal”. Dos segundos después, el cuadro de texto se establece en “Escrito por el subproceso en segundo plano \(Invoke\)”, lo que indica que se llamó al método <xref:System.Windows.Forms.Control.Invoke%2A>. Al hacer clic en el botón **Safe BW Call**, en el cuadro de texto aparece “Escrito por el subproceso principal”. Dos segundos después, el cuadro de texto se establece en “Escrito por el subproceso principal después de finalizado el subproceso en segundo plano”, lo que indica que se llamó al controlador del evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> de <xref:System.ComponentModel.BackgroundWorker>.  
  
## Programación eficaz  
  
> [!CAUTION]
>  Si usa multithreading de cualquier tipo, corre el riesgo de que se produzcan errores graves y complejos en el código. Para obtener más información, consulte [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que use multithreading.  
  
## Vea también  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)