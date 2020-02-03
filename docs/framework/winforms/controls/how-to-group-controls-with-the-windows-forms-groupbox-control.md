---
title: Agrupar controles con el control GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736658"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="ad08e-102">Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad08e-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="ad08e-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="ad08e-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="ad08e-104">Existen tres razones para agrupar los controles:</span><span class="sxs-lookup"><span data-stu-id="ad08e-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="ad08e-105">Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.</span><span class="sxs-lookup"><span data-stu-id="ad08e-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="ad08e-106">Para crear la agrupación mediante programación (de botones de radio, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ad08e-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="ad08e-107">Para mover los controles como una unidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ad08e-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="ad08e-108">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="ad08e-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="ad08e-109">Dibuja un control de <xref:System.Windows.Forms.GroupBox> en un formulario.</span><span class="sxs-lookup"><span data-stu-id="ad08e-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="ad08e-110">Agregue otros controles al cuadro de grupo y dibuje cada uno dentro del cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="ad08e-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="ad08e-111">Si tiene controles existentes que desea incluir en un cuadro de grupo, puede seleccionar todos los controles, recortarlos en el portapapeles, seleccionar el control de <xref:System.Windows.Forms.GroupBox> y, a continuación, pegarlos en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="ad08e-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="ad08e-112">También puede arrastrarlos al cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="ad08e-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="ad08e-113">Establezca la propiedad <xref:System.Windows.Forms.GroupBox.Text%2A> del cuadro de grupo en un título adecuado.</span><span class="sxs-lookup"><span data-stu-id="ad08e-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad08e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad08e-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="ad08e-115">GroupBox (control)</span><span class="sxs-lookup"><span data-stu-id="ad08e-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
