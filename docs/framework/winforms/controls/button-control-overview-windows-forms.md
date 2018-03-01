---
title: "Información general sobre el control Button (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e04b99c9d85ae92ad4d013abc01c5b16914fe1c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="button-control-overview-windows-forms"></a><span data-ttu-id="e53f7-102">Información general sobre el control Button (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e53f7-102">Button Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e53f7-103">El control <xref:System.Windows.Forms.Button> de Windows Forms permite al usuario hacer clic en él para llevar a cabo una acción.</span><span class="sxs-lookup"><span data-stu-id="e53f7-103">The Windows Forms <xref:System.Windows.Forms.Button> control allows the user to click it to perform an action.</span></span> <span data-ttu-id="e53f7-104">Al hacer clic en el botón, parece como si se hubiera presionado y soltado.</span><span class="sxs-lookup"><span data-stu-id="e53f7-104">When the button is clicked, it looks as if it is being pushed in and released.</span></span> <span data-ttu-id="e53f7-105">Cada vez que el usuario hace clic en un botón, el <xref:System.Windows.Forms.Control.Click> se invoca el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="e53f7-105">Whenever the user clicks a button, the <xref:System.Windows.Forms.Control.Click> event handler is invoked.</span></span> <span data-ttu-id="e53f7-106">Colocar código en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para realizar cualquier acción que elija.</span><span class="sxs-lookup"><span data-stu-id="e53f7-106">You place code in the <xref:System.Windows.Forms.Control.Click> event handler to perform any action you choose.</span></span>  
  
 <span data-ttu-id="e53f7-107">El texto mostrado en el botón se encuentra en la <xref:System.Windows.Forms.Control.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e53f7-107">The text displayed on the button is contained in the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="e53f7-108">Si el texto excede el ancho del botón, se ajustará a la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="e53f7-108">If your text exceeds the width of the button, it will wrap to the next line.</span></span> <span data-ttu-id="e53f7-109">Sin embargo, se recortará si el control no puede contener su altura general.</span><span class="sxs-lookup"><span data-stu-id="e53f7-109">However, it will be clipped if the control cannot accommodate its overall height.</span></span> <span data-ttu-id="e53f7-110">Para obtener más información, consulte [Cómo: establecer el texto que se muestra en un Control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="e53f7-110">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span> <span data-ttu-id="e53f7-111">El <xref:System.Windows.Forms.Control.Text%2A> propiedad puede contener una clave de acceso, que permite a un usuario para "hacer clic" en el control presionando la tecla ALT y la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="e53f7-111">The <xref:System.Windows.Forms.Control.Text%2A> property can contain an access key, which allows a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="e53f7-112">Para obtener más información, consulte [Cómo: crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e53f7-112">For details, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span> <span data-ttu-id="e53f7-113">La apariencia del texto está controlada por el <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e53f7-113">The appearance of the text is controlled by the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> property.</span></span>  
  
 <span data-ttu-id="e53f7-114">El <xref:System.Windows.Forms.Button> control también puede mostrar imágenes con la <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="e53f7-114">The <xref:System.Windows.Forms.Button> control can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="e53f7-115">Para obtener más información, consulte [Cómo: establecer la imagen muestra un Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span><span class="sxs-lookup"><span data-stu-id="e53f7-115">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53f7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e53f7-116">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="e53f7-117">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e53f7-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="e53f7-118">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e53f7-118">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="e53f7-119">Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="e53f7-119">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="e53f7-120">Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="e53f7-120">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="e53f7-121">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="e53f7-121">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
