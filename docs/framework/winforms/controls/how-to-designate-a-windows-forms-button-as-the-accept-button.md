---
title: Procedimiento Designar un botón de formularios Windows Forms como botón Aceptar
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
ms.openlocfilehash: e35dbc2b66f743f5af3c405228439268590e1a5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660208"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="c0692-102">Procedimiento Designar un botón de formularios Windows Forms como botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="c0692-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="c0692-103">En cualquier formulario de Windows, se puede designar un <xref:System.Windows.Forms.Button> que sea el botón Aceptar, también conocido como el botón predeterminado del control.</span><span class="sxs-lookup"><span data-stu-id="c0692-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="c0692-104">Cada vez que el usuario presiona la tecla ENTRAR, se hace clic en el botón predeterminado, independientemente de que otro control en el formulario tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c0692-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0692-105">Las excepciones a esto son cuando el control tiene el foco es otro botón, en ese caso, se hace clic en el botón con el foco, o un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c0692-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="c0692-106">Para designar el botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="c0692-106">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="c0692-107">Establezca el formulario <xref:System.Windows.Forms.Form.AcceptButton%2A> propiedad correspondientes <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="c0692-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0692-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0692-108">See also</span></span>
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="c0692-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="c0692-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="c0692-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0692-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="c0692-111">Cómo: Responder a clics de botón de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0692-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="c0692-112">Cómo: Designar un botón de formularios Windows Forms como botón para cancelar</span><span class="sxs-lookup"><span data-stu-id="c0692-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="c0692-113">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="c0692-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
