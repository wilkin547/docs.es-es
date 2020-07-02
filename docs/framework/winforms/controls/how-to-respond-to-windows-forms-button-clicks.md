---
title: para responder a clics de botón
description: Obtenga información sobre cómo responder a los clics de los botones de Windows Forms. El uso más básico de un control de botón de Windows Forms es ejecutar código al hacer clic en el botón.
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
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619733"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="a3102-104">Cómo: Responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3102-104">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="a3102-105">El uso más básico de un control de Windows Forms <xref:System.Windows.Forms.Button> es ejecutar código al hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="a3102-105">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="a3102-106">Al hacer clic en un <xref:System.Windows.Forms.Button> control, también se generan otros eventos, como <xref:System.Windows.Forms.Control.MouseEnter> los <xref:System.Windows.Forms.Control.MouseDown> eventos, y <xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="a3102-106">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="a3102-107">Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="a3102-107">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="a3102-108">Por ejemplo, si al hacer clic en el botón se borra la información que el usuario ha escrito en un cuadro de texto, al pausar el puntero del mouse sobre el botón, no se debería mostrar una información sobre herramientas que ahora no existe.</span><span class="sxs-lookup"><span data-stu-id="a3102-108">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="a3102-109">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.Button> control, cada clic se procesará por separado; es decir, el control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="a3102-109">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="a3102-110">Para responder a un clic de botón</span><span class="sxs-lookup"><span data-stu-id="a3102-110">To respond to a button click</span></span>  
  
- <span data-ttu-id="a3102-111">En el botón `Click` <xref:System.EventHandler> Escriba el código que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a3102-111">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="a3102-112">`Button1_Click`se debe enlazar al control.</span><span class="sxs-lookup"><span data-stu-id="a3102-112">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="a3102-113">Para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a3102-113">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3102-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3102-114">See also</span></span>

- [<span data-ttu-id="a3102-115">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="a3102-115">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="a3102-116">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3102-116">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="a3102-117">Control Button</span><span class="sxs-lookup"><span data-stu-id="a3102-117">Button Control</span></span>](button-control-windows-forms.md)
