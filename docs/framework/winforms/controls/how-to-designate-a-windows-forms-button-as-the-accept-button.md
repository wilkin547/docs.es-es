---
title: Designar un botón como botón para aceptar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743271"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="ef71c-102">Cómo: Designar un botón de Windows Forms como botón para aceptar</span><span class="sxs-lookup"><span data-stu-id="ef71c-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="ef71c-103">En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Aceptar, también conocido como el botón predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef71c-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="ef71c-104">Cada vez que el usuario presiona la tecla entrar, se hace clic en el botón predeterminado, independientemente del control del formulario que tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="ef71c-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef71c-105">Las excepciones a esto se produce cuando el control con el foco es otro botón; en ese caso, se hará clic en el botón con el foco, o en un cuadro de texto multilínea, o en un control personalizado que capture la tecla entrar.</span><span class="sxs-lookup"><span data-stu-id="ef71c-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="ef71c-106">Para designar el botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="ef71c-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="ef71c-107">Establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario en el control <xref:System.Windows.Forms.Button> adecuado.</span><span class="sxs-lookup"><span data-stu-id="ef71c-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ef71c-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef71c-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="ef71c-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="ef71c-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="ef71c-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef71c-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="ef71c-111">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef71c-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="ef71c-112">Designar un botón de Windows Forms como botón para cancelar</span><span class="sxs-lookup"><span data-stu-id="ef71c-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="ef71c-113">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="ef71c-113">Button Control</span></span>](button-control-windows-forms.md)
