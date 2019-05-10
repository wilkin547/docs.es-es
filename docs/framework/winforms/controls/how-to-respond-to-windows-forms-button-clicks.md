---
title: Procedimiento para responder a clics de botones en formularios Windows Forms
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
ms.openlocfilehash: ebcde2b5e749c5a3621c623a864578b2a654ce63
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638376"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="bfc00-102">Procedimiento para responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfc00-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="bfc00-103">El uso más básico de un formulario Windows Forms <xref:System.Windows.Forms.Button> control consiste en ejecutar código cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="bfc00-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="bfc00-104">Al hacer clic en un <xref:System.Windows.Forms.Button> control también genera un número de otros eventos, como el <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, y <xref:System.Windows.Forms.Control.MouseUp> eventos.</span><span class="sxs-lookup"><span data-stu-id="bfc00-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="bfc00-105">Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="bfc00-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="bfc00-106">Por ejemplo, si hace clic en el botón se borra la información que el usuario ha escrito en un cuadro de texto, el pausando el puntero del mouse por encima del botón debe mostrar no herramientas con esa información ahora inexistente.</span><span class="sxs-lookup"><span data-stu-id="bfc00-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="bfc00-107">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.Button> control, cada clic se procesará por separado; es decir, el control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="bfc00-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="bfc00-108">Para responder a un clic de botón</span><span class="sxs-lookup"><span data-stu-id="bfc00-108">To respond to a button click</span></span>  
  
- <span data-ttu-id="bfc00-109">En el botón `Click` <xref:System.EventHandler> escribir el código que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="bfc00-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="bfc00-110">`Button1_Click` se debe enlazar al control.</span><span class="sxs-lookup"><span data-stu-id="bfc00-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="bfc00-111">Para obtener más información, vea [Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bfc00-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bfc00-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfc00-112">See also</span></span>

- [<span data-ttu-id="bfc00-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="bfc00-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="bfc00-114">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfc00-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="bfc00-115">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="bfc00-115">Button Control</span></span>](button-control-windows-forms.md)
