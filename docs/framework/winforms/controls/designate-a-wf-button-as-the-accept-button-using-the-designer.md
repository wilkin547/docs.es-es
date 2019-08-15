---
title: Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27ecb26c493232bcfb996d012f9760b7ef91e5b2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039656"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="1d72d-102">Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1d72d-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="1d72d-103">En cualquier Windows Form, puede designar un <xref:System.Windows.Forms.Button> control para que sea el botón Aceptar, también conocido como el botón predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1d72d-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="1d72d-104">Cada vez que el usuario presiona la tecla entrar, se hace clic en el botón predeterminado, independientemente del control del formulario que tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="1d72d-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="1d72d-105">Las excepciones a esto se produce cuando el control con el foco es otro botón; en ese caso, se hará clic en el botón con el foco, o en un cuadro de texto multilínea, o en un control personalizado que capture la tecla entrar.</span><span class="sxs-lookup"><span data-stu-id="1d72d-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="1d72d-106">Para designar el botón Aceptar</span><span class="sxs-lookup"><span data-stu-id="1d72d-106">To designate the accept button</span></span>

1. <span data-ttu-id="1d72d-107">Seleccione el formulario en el que reside el botón.</span><span class="sxs-lookup"><span data-stu-id="1d72d-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="1d72d-108">En la ventana **propiedades** , establezca la propiedad del <xref:System.Windows.Forms.Form.AcceptButton%2A> formulario en el <xref:System.Windows.Forms.Button> nombre del control.</span><span class="sxs-lookup"><span data-stu-id="1d72d-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d72d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d72d-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="1d72d-110">Información general sobre el control Button</span><span class="sxs-lookup"><span data-stu-id="1d72d-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="1d72d-111">Maneras de seleccionar un control Button de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1d72d-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="1d72d-112">Cómo: Responder a clics de botón de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1d72d-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1d72d-113">Cómo: Designar un botón de Windows Forms como botón para cancelar mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1d72d-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="1d72d-114">Botón (control)</span><span class="sxs-lookup"><span data-stu-id="1d72d-114">Button Control</span></span>](button-control-windows-forms.md)
