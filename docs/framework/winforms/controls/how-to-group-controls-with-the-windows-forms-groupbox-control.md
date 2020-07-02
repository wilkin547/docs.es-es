---
title: Agrupar controles con el control GroupBox
description: Aprenda a agrupar controles con el control Windows Forms GroupBox para que pueda crear una agrupación visual de elementos relacionados.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618069"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="7450c-103">Procedimiento para agrupar controles con el control GroupBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7450c-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="7450c-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="7450c-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="7450c-105">Existen tres razones para agrupar los controles:</span><span class="sxs-lookup"><span data-stu-id="7450c-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="7450c-106">Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.</span><span class="sxs-lookup"><span data-stu-id="7450c-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="7450c-107">Para crear la agrupación mediante programación (de botones de radio, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="7450c-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="7450c-108">Para mover los controles como una unidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="7450c-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="7450c-109">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="7450c-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="7450c-110">Dibuje un <xref:System.Windows.Forms.GroupBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="7450c-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="7450c-111">Agregue otros controles al cuadro de grupo y dibuje cada uno dentro del cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="7450c-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="7450c-112">Si tiene controles existentes que desea incluir en un cuadro de grupo, puede seleccionar todos los controles, recortarlos en el portapapeles, seleccionar el <xref:System.Windows.Forms.GroupBox> control y, a continuación, pegarlos en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="7450c-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="7450c-113">También puede arrastrarlos al cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="7450c-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="7450c-114">Establezca la <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo en un título adecuado.</span><span class="sxs-lookup"><span data-stu-id="7450c-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7450c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7450c-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="7450c-116">Control GroupBox</span><span class="sxs-lookup"><span data-stu-id="7450c-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
