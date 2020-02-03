---
title: Determinar en qué panel del control StatusBar se hizo clic
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746015"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="e7278-102">Cómo: Determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="e7278-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e7278-103">Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="e7278-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e7278-104">Para programar el control de [control StatusBar](statusbar-control-windows-forms.md) para responder a los clics del usuario, use una instrucción Case dentro del evento <xref:System.Windows.Forms.StatusBar.PanelClick>.</span><span class="sxs-lookup"><span data-stu-id="e7278-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="e7278-105">El evento contiene un argumento (el argumento del panel), que contiene una referencia al <xref:System.Windows.Forms.StatusBarPanel>en el que se ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="e7278-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="e7278-106">Con esta referencia, puede determinar el índice del panel en el que se ha hecho clic y programar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="e7278-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7278-107">Asegúrese de que la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> del control <xref:System.Windows.Forms.StatusBar> esté establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="e7278-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="e7278-108">Para determinar en qué panel se hizo clic</span><span class="sxs-lookup"><span data-stu-id="e7278-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="e7278-109">En el controlador de eventos <xref:System.Windows.Forms.StatusBar.PanelClick>, use una instrucción `Select Case` (en Visual Basic) o `switch case` C# (visual C++o visual) para determinar en qué panel se hizo clic examinando el índice del panel en el que se hizo clic en los argumentos del evento.</span><span class="sxs-lookup"><span data-stu-id="e7278-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="e7278-110">En el ejemplo de código siguiente se requiere la presencia, en el formulario, de un <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`y dos objetos <xref:System.Windows.Forms.StatusBarPanel>, `StatusBarPanel1` y `StatusBarPanel2`.</span><span class="sxs-lookup"><span data-stu-id="e7278-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="e7278-111">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="e7278-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e7278-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7278-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="e7278-113">Establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="e7278-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="e7278-114">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e7278-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="e7278-115">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="e7278-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
