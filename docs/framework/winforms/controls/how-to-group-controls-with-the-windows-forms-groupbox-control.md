---
title: Procedimiento Agrupar controles con el Control GroupBox de formularios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: 44f0116511165c021f8e3dc35fb14e5cfb6f619e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686925"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="65fd0-102">Procedimiento Agrupar controles con el Control GroupBox de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="65fd0-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="65fd0-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="65fd0-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="65fd0-104">Existen tres razones para controles de grupo:</span><span class="sxs-lookup"><span data-stu-id="65fd0-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="65fd0-105">Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.</span><span class="sxs-lookup"><span data-stu-id="65fd0-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="65fd0-106">Para crear la agrupación de programación (de botones de radio, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="65fd0-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="65fd0-107">Para mover los controles como una unidad de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="65fd0-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="65fd0-108">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="65fd0-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="65fd0-109">Dibujar un <xref:System.Windows.Forms.GroupBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="65fd0-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="65fd0-110">Agregue otros controles en el cuadro de grupo, cada uno dentro del cuadro de grupo de dibujo.</span><span class="sxs-lookup"><span data-stu-id="65fd0-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="65fd0-111">Si tiene controles que desee incluir en un cuadro de grupo, puede seleccionar todos los controles, cortarlos en el Portapapeles, seleccione el <xref:System.Windows.Forms.GroupBox> controlar y, a continuación, péguelos en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="65fd0-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="65fd0-112">También puede arrastrar en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="65fd0-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="65fd0-113">Establecer el <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo para el título apropiado.</span><span class="sxs-lookup"><span data-stu-id="65fd0-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fd0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="65fd0-114">See also</span></span>
- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="65fd0-115">GroupBox (control)</span><span class="sxs-lookup"><span data-stu-id="65fd0-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
