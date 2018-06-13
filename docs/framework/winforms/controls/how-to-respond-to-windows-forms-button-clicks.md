---
title: 'Cómo: Responder a clics de botones en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 14a880c34f163dc6fece44c24d377822a741b0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534256"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="e22dc-102">Cómo: Responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e22dc-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="e22dc-103">El uso más básico de Windows Forms <xref:System.Windows.Forms.Button> control consiste en ejecutar código cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="e22dc-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="e22dc-104">Al hacer clic en un <xref:System.Windows.Forms.Button> control también genera un número de otros eventos, como el <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, y <xref:System.Windows.Forms.Control.MouseUp> eventos.</span><span class="sxs-lookup"><span data-stu-id="e22dc-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="e22dc-105">Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="e22dc-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="e22dc-106">Por ejemplo, si hace clic en el botón se borra la información escrita por el usuario en un cuadro de texto, el al situar el puntero del mouse sobre el botón debería mostrar no una información sobre herramientas con esa información ahora inexistente.</span><span class="sxs-lookup"><span data-stu-id="e22dc-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="e22dc-107">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.Button> control, cada clic se procesará por separado; es decir, el control no admite el evento doble clic.</span><span class="sxs-lookup"><span data-stu-id="e22dc-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="e22dc-108">Para responder a un clic del botón</span><span class="sxs-lookup"><span data-stu-id="e22dc-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="e22dc-109">En el botón `Click` <xref:System.EventHandler> escribir el código que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e22dc-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="e22dc-110">`Button1_Click` se debe enlazar al control.</span><span class="sxs-lookup"><span data-stu-id="e22dc-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="e22dc-111">Para obtener más información, consulte [Cómo: crear controladores de eventos en tiempo de ejecución para formularios Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e22dc-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e22dc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e22dc-112">See Also</span></span>  
 [<span data-ttu-id="e22dc-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="e22dc-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="e22dc-114">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e22dc-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="e22dc-115">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="e22dc-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
