---
title: Designar un botón como botón para cancelar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743263"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="44fd7-102">Cómo: Designar un botón de Windows Forms como botón para cancelar</span><span class="sxs-lookup"><span data-stu-id="44fd7-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="44fd7-103">En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="44fd7-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="44fd7-104">Se hace clic en un botón Cancelar cuando el usuario presiona la tecla ESC, independientemente del control del formulario que tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="44fd7-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="44fd7-105">Normalmente, este botón se programa para permitir al usuario salir rápidamente de una operación sin confirmar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="44fd7-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="44fd7-106">Para designar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="44fd7-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="44fd7-107">Establezca la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> del formulario en el control <xref:System.Windows.Forms.Button> adecuado.</span><span class="sxs-lookup"><span data-stu-id="44fd7-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="44fd7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="44fd7-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="44fd7-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="44fd7-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="44fd7-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44fd7-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="44fd7-111">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44fd7-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="44fd7-112">Designar un botón de Windows Forms como botón para aceptar</span><span class="sxs-lookup"><span data-stu-id="44fd7-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="44fd7-113">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="44fd7-113">Button Control</span></span>](button-control-windows-forms.md)
