---
title: 'Cómo: Agregar paneles a un control StatusBar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: dd006f669ab6f0186bbcc7d1c76f9852ab6e8f60
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45617664"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a>Cómo: Agregar paneles a un control StatusBar
> [!IMPORTANT]
>  El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.  
  
 El área programable dentro de un [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control consta de las instancias de la <xref:System.Windows.Forms.StatusBarPanel> clase. Se agregan a través de las adiciones a la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> clase.  
  
### <a name="to-add-panels-to-a-status-bar"></a>Para agregar paneles a una barra de estado  
  
1.  En un procedimiento, cree paneles de barra de estado agregándolos a la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>. Especifique los valores de propiedad para paneles individuales utilizando su índice se pasan a través de la <xref:System.Windows.Forms.StatusBar.Panels%2A> propiedad.  
  
     En el ejemplo de código siguiente establece la ruta de acceso para la ubicación del icono es el **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecutan el sistema operativo de Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente requiere un formulario con un <xref:System.Windows.Forms.StatusBar> control ya se ha agregado.  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> es una colección basada en cero, por lo que el código debería proceder en consecuencia.  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Cuadro de diálogo Editor de colección](https://msdn.microsoft.com/library/53fb3aad-bffa-4da5-ac89-8438e6fc803c)  
 [Establecer el tamaño de los paneles de la barra de estado](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Determinar en qué panel del control StatusBar de Windows Forms se hizo clic](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Información general sobre StatusBar (Control)](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
