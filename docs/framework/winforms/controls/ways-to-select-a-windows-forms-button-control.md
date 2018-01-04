---
title: Maneras de seleccionar un control Button de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b6fa31b89b8fbe50077933cf04aa3c17db86438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="fd878-102">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd878-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="fd878-103">Se pueden seleccionar un botón de formularios Windows Forms en las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="fd878-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="fd878-104">Usar un mouse para hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="fd878-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="fd878-105">Invocar el botón <xref:System.Windows.Forms.Control.Click> evento en el código.</span><span class="sxs-lookup"><span data-stu-id="fd878-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="fd878-106">Mover el foco al botón presionando la tecla TAB y, a continuación, elija el botón al presionar la barra espaciadora o ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fd878-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="fd878-107">Presione la tecla de acceso (ALT + letra subrayada) del botón.</span><span class="sxs-lookup"><span data-stu-id="fd878-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="fd878-108">Para obtener más información acerca de las teclas de acceso, consulte [Cómo: crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="fd878-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="fd878-109">Si el botón es el botón "Aceptar" del formulario, al presionar ENTRAR, elige el botón, aunque otro control tenga el foco, excepto si ese control es otro botón, un cuadro de texto de varias líneas o un control personalizado que intercepta la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fd878-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="fd878-110">Si el botón es el botón "Cancelar" del formulario, al presionar ESC elige el botón, aunque otro control tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="fd878-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="fd878-111">Llame a la <xref:System.Windows.Forms.Button.PerformClick%2A> método para seleccionar el botón mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fd878-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd878-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd878-112">See Also</span></span>  
 [<span data-ttu-id="fd878-113">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="fd878-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd878-114">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd878-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="fd878-115">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="fd878-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
