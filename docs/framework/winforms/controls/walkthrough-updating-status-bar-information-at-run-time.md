---
title: "Tutorial: Actualizar la informaci&#243;n de la barra de estado en tiempo de ejecuci&#243;n | Microsoft Docs"
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
  - "paneles, actualizar la barra de estado"
  - "barras de estado, actualizar paneles"
  - "barras de estado, actualizar en tiempo de ejecución"
  - "StatusBar (control) [Windows Forms], actualizar paneles"
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Tutorial: Actualizar la informaci&#243;n de la barra de estado en tiempo de ejecuci&#243;n
> [!IMPORTANT]
>  Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>, y les agregan funcionalidad; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan para obtener la compatibilidad con versiones anteriores y para su uso futuro, si se desea.  
  
 Con frecuencia, el programa le solicitará que actualice el contenido de los paneles de la barra de estado dinámicamente en tiempo de ejecución, basándose en cambios en el estado de la aplicación u otra interacción del usuario.  Esta es una manera común de indicar a los usuarios que las teclas como BLOQ MAYÚS, BLOQ NUM o BLOQ DESPL están habilitadas o para proporcionar la fecha o un reloj como una referencia adecuada.  
  
 En el ejemplo siguiente, se utiliza una instancia de la clase <xref:System.Windows.Forms.StatusBarPanel> para hospedar un reloj.  
  
### Para obtener la barra de estado lista para la actualización  
  
1.  Cree un nuevo formulario Windows Forms.  
  
2.  Agregue el control <xref:System.Windows.Forms.StatusBar> al formulario.  Para obtener información detallada, vea [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
3.  Agregue un panel de barra de estado al control <xref:System.Windows.Forms.StatusBar>.  Para obtener información detallada, vea [Cómo: Agregar paneles a un control StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).  
  
4.  Para el control <xref:System.Windows.Forms.StatusBar> que ha agregado a su formulario, establezca la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `true`.  
  
5.  Agregue al formulario un componente <xref:System.Windows.Forms.Timer> de formularios Windows Forms.  
  
    > [!NOTE]
    >  El componente <xref:System.Windows.Forms.Timer?displayProperty=fullName> de formularios Windows Forms está diseñado para el entorno de formularios Windows Forms.  Si necesita un temporizador que sea adecuado para un entorno de servidor, vea [Introduction to Server\-Based Timers](http://msdn.microsoft.com/es-es/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
6.  Establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true`.  
  
7.  Establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> del control <xref:System.Windows.Forms.Timer> en 30000.  
  
    > [!NOTE]
    >  La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> del componente <xref:System.Windows.Forms.Timer> se establece en 30 segundos \(30.000 milisegundos\) para asegurarse de que la hora mostrada sea exacta.  
  
### Para implementar el temporizador para actualizar la barra de estado  
  
1.  Inserte el código siguiente en el controlador de eventos del componente <xref:System.Windows.Forms.Timer> para actualizar el panel del control <xref:System.Windows.Forms.StatusBar>.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     En este punto, puede ejecutar la aplicación; observará el reloj en ejecución en el panel de barra de estado.  
  
### Para probar la aplicación  
  
1.  Depure la aplicación y presione F5 para ejecutarla.  Para obtener información sobre la depuración, vea [Depurar en Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
    > [!NOTE]
    >  El reloj tardará aproximadamente 30 segundos en aparecer en la barra de estado.  Esto es así para obtener la hora más precisa posible.  Por otro lado, para que el reloj aparezca antes, puede reducir el valor de la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> que ha establecido en el paso 7 del procedimiento anterior.  
  
## Vea también  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Cómo: Agregar paneles a un control StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)   
 [Cómo: Determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Información general sobre StatusBar \(Control\)](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)