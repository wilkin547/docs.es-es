---
title: "C&#243;mo: Establecer el tama&#241;o de los paneles de la barra de estado | Microsoft Docs"
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
  - "paneles, establecer el tamaño de las barras de estado"
  - "barras de estado, establecer el tamaño de un panel"
  - "StatusBar (control) [Windows Forms], tamaño de panel"
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer el tama&#241;o de los paneles de la barra de estado
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStripStatusLabel> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.StatusBar>, este control <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Cada instancia de la clase <xref:System.Windows.Forms.StatusBarPanel> dentro de un control [StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) tiene un número de propiedades dinámicas que determinan su ancho y el comportamiento de cambio de tamaño en tiempo de ejecución.  
  
### Para establecer el tamaño de un panel  
  
1.  En un procedimiento, establezca las propiedades <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A> y <xref:System.Windows.Forms.StatusBarPanel.Width%2A> \(o cualquier subconjunto incluido\) para los paneles de barra de estado utilizando su índice pasado a la propiedad <xref:System.Windows.Forms.StatusBar.Panels%2A> de la colección <xref:System.Windows.Forms.StatusBarPanel>.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Cómo: Determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Información general sobre StatusBar \(Control\)](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)