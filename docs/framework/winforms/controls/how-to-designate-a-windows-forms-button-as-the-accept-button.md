---
title: Designar un botón como el botón Aceptar
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142152"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="aadf9-102">Cómo: Designar un botón de formularios Windows Forms como botón para aceptar</span><span class="sxs-lookup"><span data-stu-id="aadf9-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="aadf9-103">En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> control para que sea el botón Aceptar, también conocido como el botón predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aadf9-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="aadf9-104">Cada vez que el usuario presiona la tecla ENTRAR, se hace clic en el botón predeterminado independientemente del otro control del formulario que tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="aadf9-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aadf9-105">Las excepciones a esto son cuando el control con foco es otro botón (en ese caso, se hará clic en el botón con el foco) o un cuadro de texto de varias líneas, o un control personalizado que captura la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="aadf9-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="aadf9-106">Para designar el botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="aadf9-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="aadf9-107">Establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario <xref:System.Windows.Forms.Button> en el control adecuado.</span><span class="sxs-lookup"><span data-stu-id="aadf9-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aadf9-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aadf9-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="aadf9-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="aadf9-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="aadf9-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aadf9-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="aadf9-111">Cómo: Responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aadf9-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="aadf9-112">Cómo: Definir un botón de formularios Windows Forms como el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="aadf9-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="aadf9-113">Control Button</span><span class="sxs-lookup"><span data-stu-id="aadf9-113">Button Control</span></span>](button-control-windows-forms.md)
