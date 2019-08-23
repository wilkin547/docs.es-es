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
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="16c06-102">Procedimiento para determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="16c06-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="16c06-103">Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.</span><span class="sxs-lookup"><span data-stu-id="16c06-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="16c06-104">Para programar el control de [control StatusBar](statusbar-control-windows-forms.md) para responder a los clics del usuario, use una instrucción <xref:System.Windows.Forms.StatusBar.PanelClick> Case dentro del evento.</span><span class="sxs-lookup"><span data-stu-id="16c06-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="16c06-105">El evento contiene un argumento (el argumento del panel), que contiene una referencia al clic <xref:System.Windows.Forms.StatusBarPanel>.</span><span class="sxs-lookup"><span data-stu-id="16c06-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="16c06-106">Con esta referencia, puede determinar el índice del panel en el que se ha hecho clic y programar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="16c06-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16c06-107">Asegúrese de que <xref:System.Windows.Forms.StatusBar> la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> del control está establecida `true`en.</span><span class="sxs-lookup"><span data-stu-id="16c06-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="16c06-108">Para determinar en qué panel se hizo clic</span><span class="sxs-lookup"><span data-stu-id="16c06-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="16c06-109">En el <xref:System.Windows.Forms.StatusBar.PanelClick> controlador de eventos, use `Select Case` una instrucción (en Visual Basic `switch case` ) o C# (visual C++o visual) para determinar en qué panel se hizo clic examinando el índice del panel en el que se hizo clic en los argumentos del evento.</span><span class="sxs-lookup"><span data-stu-id="16c06-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="16c06-110">En el ejemplo de código siguiente se requiere la presencia, en el formulario <xref:System.Windows.Forms.StatusBar> , de `StatusBar1`un control, <xref:System.Windows.Forms.StatusBarPanel> y dos `StatusBarPanel1` objetos `StatusBarPanel2`, y.</span><span class="sxs-lookup"><span data-stu-id="16c06-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="16c06-111">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="16c06-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16c06-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="16c06-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="16c06-113">Cómo: Establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="16c06-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="16c06-114">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="16c06-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="16c06-115">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="16c06-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
