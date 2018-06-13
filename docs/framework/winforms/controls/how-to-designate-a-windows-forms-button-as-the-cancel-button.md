---
title: 'Cómo: Definir un botón de formularios Windows Forms como el botón Cancelar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: efe68ec8e5c34607bb8f865b5d0c7919a0377ab8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530876"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="9710a-102">Cómo: Definir un botón de formularios Windows Forms como el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="9710a-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="9710a-103">En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> que sea el botón Cancelar del control.</span><span class="sxs-lookup"><span data-stu-id="9710a-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="9710a-104">Cada vez que el usuario presiona la tecla ESC, sin tener en cuenta que otro control en el formulario tiene el foco, se hace clic en un botón de cancelación.</span><span class="sxs-lookup"><span data-stu-id="9710a-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="9710a-105">Habitualmente, este botón se programa para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9710a-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="9710a-106">Para designar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="9710a-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="9710a-107">Establezca el formulario <xref:System.Windows.Forms.Form.CancelButton%2A> propiedad correspondientes <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="9710a-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9710a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9710a-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="9710a-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="9710a-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="9710a-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9710a-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="9710a-111">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9710a-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="9710a-112">Designar un botón de Windows Forms como botón para aceptar</span><span class="sxs-lookup"><span data-stu-id="9710a-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [<span data-ttu-id="9710a-113">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="9710a-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
