---
title: Procedimiento para establecer el tamaño de los paneles de la barra de estado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: 4ba0f7f02b548a5d9ea1a99605a668f449b3e4a9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923624"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Procedimiento para establecer el tamaño de los paneles de la barra de estado
> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStripStatusLabel> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.StatusBar>; sin embargo, el control <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Cada instancia de la <xref:System.Windows.Forms.StatusBarPanel> clase dentro de un control de [control StatusBar](statusbar-control-windows-forms.md) tiene varias propiedades dinámicas que determinan su ancho y el comportamiento de ajuste de tamaño en tiempo de ejecución.  
  
### <a name="to-set-the-size-of-a-panel"></a>Para establecer el tamaño de un panel  
  
1. En un procedimiento, establezca las <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>propiedades <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, y <xref:System.Windows.Forms.StatusBarPanel.Width%2A> (o cualquier subconjunto que contenga) para los paneles de la barra de estado usando su índice <xref:System.Windows.Forms.StatusBar.Panels%2A> pasado a través <xref:System.Windows.Forms.StatusBarPanel> de la propiedad de la colección.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución](walkthrough-updating-status-bar-information-at-run-time.md)
- [Procedimientos: Determinar en qué panel del control Windows Forms StatusBar se hizo clic](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Información general sobre StatusBar (Control)](statusbar-control-overview-windows-forms.md)
