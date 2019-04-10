---
title: Filtrar para designar un botón de formularios Windows Forms como botón para cancelar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: ad95a527ea72858cc106c87d8712110e018e97b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231440"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="062d5-102">Filtrar para designar un botón de formularios Windows Forms como botón para cancelar</span><span class="sxs-lookup"><span data-stu-id="062d5-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="062d5-103">En cualquier formulario de Windows, se puede designar un <xref:System.Windows.Forms.Button> que sea el botón Cancelar del control.</span><span class="sxs-lookup"><span data-stu-id="062d5-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="062d5-104">Cada vez que el usuario presiona la tecla ESC, independientemente de que otro control en el formulario tiene el foco, se hace clic en un botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="062d5-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="062d5-105">Habitualmente se programa un botón para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="062d5-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="062d5-106">Para designar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="062d5-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="062d5-107">Establezca el formulario <xref:System.Windows.Forms.Form.CancelButton%2A> propiedad correspondientes <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="062d5-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="062d5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="062d5-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="062d5-109">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="062d5-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="062d5-110">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="062d5-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="062d5-111">Filtrar para responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="062d5-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="062d5-112">Filtrar para designar un botón de formularios Windows Forms como botón para aceptar</span><span class="sxs-lookup"><span data-stu-id="062d5-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="062d5-113">Control Button</span><span class="sxs-lookup"><span data-stu-id="062d5-113">Button Control</span></span>](button-control-windows-forms.md)
