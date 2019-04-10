---
title: Filtrar para agrupar controles con el control GroupBox de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: d2bad0020d18cd262bc2fe3489a00209308bd7b9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335880"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="20240-102">Filtrar para agrupar controles con el control GroupBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20240-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="20240-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="20240-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="20240-104">Existen tres razones para controles de grupo:</span><span class="sxs-lookup"><span data-stu-id="20240-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="20240-105">Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.</span><span class="sxs-lookup"><span data-stu-id="20240-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="20240-106">Para crear la agrupación de programación (de botones de radio, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="20240-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="20240-107">Para mover los controles como una unidad de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="20240-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="20240-108">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="20240-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="20240-109">Dibujar un <xref:System.Windows.Forms.GroupBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="20240-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="20240-110">Agregue otros controles en el cuadro de grupo, cada uno dentro del cuadro de grupo de dibujo.</span><span class="sxs-lookup"><span data-stu-id="20240-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="20240-111">Si tiene controles que desee incluir en un cuadro de grupo, puede seleccionar todos los controles, cortarlos en el Portapapeles, seleccione el <xref:System.Windows.Forms.GroupBox> controlar y, a continuación, péguelos en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="20240-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="20240-112">También puede arrastrar en el cuadro de grupo.</span><span class="sxs-lookup"><span data-stu-id="20240-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="20240-113">Establecer el <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo para el título apropiado.</span><span class="sxs-lookup"><span data-stu-id="20240-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20240-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="20240-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="20240-115">Control GroupBox</span><span class="sxs-lookup"><span data-stu-id="20240-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
