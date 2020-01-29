---
title: para responder a clics de botón
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
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735715"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="d0bbe-102">Cómo: Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d0bbe-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="d0bbe-103">El uso más básico de un control de Windows Forms <xref:System.Windows.Forms.Button> es ejecutar código al hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="d0bbe-104">Al hacer clic en un control de <xref:System.Windows.Forms.Button> también se generan otros eventos, como los eventos <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>y <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="d0bbe-105">Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="d0bbe-106">Por ejemplo, si al hacer clic en el botón se borra la información que el usuario ha escrito en un cuadro de texto, al pausar el puntero del mouse sobre el botón, no se debería mostrar una información sobre herramientas que ahora no existe.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="d0bbe-107">Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.Button>, cada clic se procesará por separado. es decir, el control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="d0bbe-108">Para responder a un clic de botón</span><span class="sxs-lookup"><span data-stu-id="d0bbe-108">To respond to a button click</span></span>  
  
- <span data-ttu-id="d0bbe-109">En el `Click` del botón <xref:System.EventHandler> escriba el código que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="d0bbe-110">`Button1_Click` debe estar enlazado al control.</span><span class="sxs-lookup"><span data-stu-id="d0bbe-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="d0bbe-111">Para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d0bbe-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0bbe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0bbe-112">See also</span></span>

- [<span data-ttu-id="d0bbe-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="d0bbe-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="d0bbe-114">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d0bbe-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="d0bbe-115">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="d0bbe-115">Button Control</span></span>](button-control-windows-forms.md)
