---
title: Maneras de seleccionar un control Button de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223295"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="40c6d-102">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40c6d-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="40c6d-103">Un botón de Windows Forms se puede seleccionar en las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="40c6d-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="40c6d-104">Usar un mouse para hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="40c6d-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="40c6d-105">Invocar el botón <xref:System.Windows.Forms.Control.Click> evento en el código.</span><span class="sxs-lookup"><span data-stu-id="40c6d-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="40c6d-106">Mover el foco al botón presionando la tecla TAB y, a continuación, elija el botón presionando la barra espaciadora o ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="40c6d-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="40c6d-107">Presione la tecla de acceso (ALT + la letra subrayada) para el botón.</span><span class="sxs-lookup"><span data-stu-id="40c6d-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="40c6d-108">Para obtener más información acerca de las claves de acceso, consulte [Cómo: Crear teclas de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="40c6d-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="40c6d-109">Si el botón es el botón "accept" del formulario, al presionar ENTRAR, elige el botón, aunque otro control tiene el foco, excepto si ese control es otro botón, un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="40c6d-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="40c6d-110">Si el botón es el botón "Cancelar" del formulario, presione ESC elige el botón, aunque otro control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="40c6d-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="40c6d-111">Llame a la <xref:System.Windows.Forms.Button.PerformClick%2A> método para seleccionar el botón mediante programación.</span><span class="sxs-lookup"><span data-stu-id="40c6d-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c6d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c6d-112">See also</span></span>

- [<span data-ttu-id="40c6d-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="40c6d-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="40c6d-114">Filtrar para responder a clics de botones en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40c6d-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="40c6d-115">Control Button</span><span class="sxs-lookup"><span data-stu-id="40c6d-115">Button Control</span></span>](button-control-windows-forms.md)
