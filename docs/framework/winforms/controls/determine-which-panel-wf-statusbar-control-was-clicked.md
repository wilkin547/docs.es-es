---
title: "C&#243;mo: Determinar en qu&#233; panel del control StatusBar de formularios Windows Forms se hizo clic | Microsoft Docs"
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
  - "Panel (control) [Windows Forms], determinar dónde se ha hecho clic"
  - "PanelClick (evento), determinar en qué panel se ha hecho clic"
  - "paneles, determinar dónde se ha hecho clic"
  - "barras de estado, determinar en qué panel se ha hecho clic"
  - "StatusBar (control) [Windows Forms], codificar los eventos de clic en los paneles"
  - "StatusBar (control) [Windows Forms], determinar en qué panel se ha hecho clic"
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Determinar en qu&#233; panel del control StatusBar de formularios Windows Forms se hizo clic
> [!IMPORTANT]
>  Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>, y les agregan funcionalidad; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan para obtener la compatibilidad con versiones anteriores y para su uso futuro, si se desea.  
  
 Para programar el control [StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) de modo que responda a los clics del usuario, utilice una instrucción case dentro del evento <xref:System.Windows.Forms.StatusBar.PanelClick>.  El evento contiene un argumento \(el argumento del panel\), que contiene una referencia al objeto <xref:System.Windows.Forms.StatusBarPanel> en el que se hizo clic.  Con esta referencia, puede determinar el índice del panel en el que ha hecho clic y el programa consecuentemente.  
  
> [!NOTE]
>  Asegúrese de que la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> del control <xref:System.Windows.Forms.StatusBar> esté establecida en `true`.  
  
### Para determinar en qué panel se hizo clic  
  
1.  En el controlador de eventos <xref:System.Windows.Forms.StatusBar.PanelClick>, utilice una instrucción `Select Case` \(en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) o `switch case` \(en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] o [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) para determinar en cuál de los paneles se ha hecho clic examinando el índice del panel con clic en los argumentos del evento.  
  
     El ejemplo de código siguiente requiere la presencia, en el formulario, de un control <xref:System.Windows.Forms.StatusBar>, `StatusBar1`, y dos objetos <xref:System.Windows.Forms.StatusBarPanel>, `StatusBarPanel1`  y `StatusBarPanel2`.  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Cómo: Establecer el tamaño de los paneles de la barra de estado](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Información general sobre StatusBar \(Control\)](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)