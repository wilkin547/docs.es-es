---
title: Maneras de seleccionar un control de botón
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740002"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="1bcff-102">Maneras de seleccionar un control Button de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1bcff-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="1bcff-103">Se puede seleccionar un botón Windows Forms de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="1bcff-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="1bcff-104">Use un mouse para hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="1bcff-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="1bcff-105">Invocar el evento <xref:System.Windows.Forms.Control.Click> del botón en el código.</span><span class="sxs-lookup"><span data-stu-id="1bcff-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="1bcff-106">Mueva el foco al botón presionando la tecla TAB y, a continuación, elija el botón presionando la barra ESPACIAdora o entrar.</span><span class="sxs-lookup"><span data-stu-id="1bcff-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="1bcff-107">Presione la tecla de acceso (ALT + la letra subrayada) para el botón.</span><span class="sxs-lookup"><span data-stu-id="1bcff-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="1bcff-108">Para obtener más información acerca de las claves de acceso, consulte [Cómo: crear claves de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1bcff-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="1bcff-109">Si el botón es el botón "Aceptar" del formulario, al presionar entrar, se elige el botón, aunque otro control tenga el foco, excepto si ese control es otro botón, un cuadro de texto de varias líneas o un control personalizado que intercepta la tecla entrar.</span><span class="sxs-lookup"><span data-stu-id="1bcff-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="1bcff-110">Si el botón es el botón "Cancelar" del formulario, al presionar ESC se elige el botón, aunque otro control tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="1bcff-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="1bcff-111">Llame al método <xref:System.Windows.Forms.Button.PerformClick%2A> para seleccionar el botón mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1bcff-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcff-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bcff-112">See also</span></span>

- [<span data-ttu-id="1bcff-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="1bcff-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="1bcff-114">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1bcff-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1bcff-115">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="1bcff-115">Button Control</span></span>](button-control-windows-forms.md)
