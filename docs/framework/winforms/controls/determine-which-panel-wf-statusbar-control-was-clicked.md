---
title: Procedimiento para determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: 6229d8965949641105cd0e9708474c3249d52d1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965720"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Procedimiento para determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic
> [!IMPORTANT]
> Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.  
  
 Para programar el control de [control StatusBar](statusbar-control-windows-forms.md) para responder a los clics del usuario, use una instrucción <xref:System.Windows.Forms.StatusBar.PanelClick> Case dentro del evento. El evento contiene un argumento (el argumento del panel), que contiene una referencia al clic <xref:System.Windows.Forms.StatusBarPanel>. Con esta referencia, puede determinar el índice del panel en el que se ha hecho clic y programar en consecuencia.  
  
> [!NOTE]
> Asegúrese de que <xref:System.Windows.Forms.StatusBar> la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> del control está establecida `true`en.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Para determinar en qué panel se hizo clic  
  
1. En el <xref:System.Windows.Forms.StatusBar.PanelClick> controlador de eventos, use `Select Case` una instrucción (en Visual Basic `switch case` ) o C# (visual C++o visual) para determinar en qué panel se hizo clic examinando el índice del panel en el que se hizo clic en los argumentos del evento.  
  
     En el ejemplo de código siguiente se requiere la presencia, en el formulario <xref:System.Windows.Forms.StatusBar> , de `StatusBar1`un control, <xref:System.Windows.Forms.StatusBarPanel> y dos `StatusBarPanel1` objetos `StatusBarPanel2`, y.  
  
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
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Cómo: Establecer el tamaño de los paneles de la barra de estado](how-to-set-the-size-of-status-bar-panels.md)
- [Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución](walkthrough-updating-status-bar-information-at-run-time.md)
- [Información general sobre StatusBar (Control)](statusbar-control-overview-windows-forms.md)
