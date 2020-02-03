---
title: Designar un botón como botón para cancelar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746054"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="352aa-102">Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="352aa-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="352aa-103">En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="352aa-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="352aa-104">Se hace clic en un botón Cancelar cuando el usuario presiona la tecla ESC, independientemente del control del formulario que tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="352aa-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="352aa-105">Normalmente, este botón se programa para permitir al usuario salir rápidamente de una operación sin confirmar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="352aa-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="352aa-106">Para designar el botón Cancelar</span><span class="sxs-lookup"><span data-stu-id="352aa-106">To designate the cancel button</span></span>

1. <span data-ttu-id="352aa-107">Seleccione el formulario en el que reside el botón.</span><span class="sxs-lookup"><span data-stu-id="352aa-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="352aa-108">En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> del formulario en el nombre del control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="352aa-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="352aa-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="352aa-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="352aa-110">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="352aa-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="352aa-111">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="352aa-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="352aa-112">Responder a clics de botones en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="352aa-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="352aa-113">Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="352aa-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="352aa-114">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="352aa-114">Button Control</span></span>](button-control-windows-forms.md)
