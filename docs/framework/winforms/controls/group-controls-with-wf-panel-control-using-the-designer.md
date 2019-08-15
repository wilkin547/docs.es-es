---
title: Procedimiento para agrupar controles con el control Panel de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040387"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="69fa9-102">Procedimiento para agrupar controles con el control Panel de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="69fa9-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="69fa9-103">Windows Forms <xref:System.Windows.Forms.Panel> controles se usan para agrupar otros controles.</span><span class="sxs-lookup"><span data-stu-id="69fa9-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="69fa9-104">Hay tres razones para agrupar los controles.</span><span class="sxs-lookup"><span data-stu-id="69fa9-104">There are three reasons to group controls.</span></span> <span data-ttu-id="69fa9-105">Una es la agrupación visual de los elementos de formulario relacionados para una interfaz de usuario clara; otro es la agrupación mediante programación, de botones de radio, por ejemplo; la última es para mover los controles como una unidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="69fa9-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="69fa9-106">Para crear un grupo de controles</span><span class="sxs-lookup"><span data-stu-id="69fa9-106">To create a group of controls</span></span>

1. <span data-ttu-id="69fa9-107">Arrastre un <xref:System.Windows.Forms.Panel> control desde la pestaña **Windows Forms** del cuadro de herramientas hasta un formulario.</span><span class="sxs-lookup"><span data-stu-id="69fa9-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="69fa9-108">Agregue otros controles al panel y dibuje cada uno dentro del panel.</span><span class="sxs-lookup"><span data-stu-id="69fa9-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="69fa9-109">Si tiene controles existentes que desea incluir en un panel, puede seleccionar todos los controles, recortarlos en el portapapeles, seleccionar el <xref:System.Windows.Forms.Panel> control y, a continuación, pegarlos en el panel.</span><span class="sxs-lookup"><span data-stu-id="69fa9-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="69fa9-110">También puede arrastrarlos al panel.</span><span class="sxs-lookup"><span data-stu-id="69fa9-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="69fa9-111">Opta Si desea agregar un borde a un panel, establezca su <xref:System.Windows.Forms.BorderStyle> propiedad.</span><span class="sxs-lookup"><span data-stu-id="69fa9-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="69fa9-112">Hay tres opciones: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>y <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="69fa9-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="69fa9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="69fa9-113">See also</span></span>

- [<span data-ttu-id="69fa9-114">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="69fa9-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="69fa9-115">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="69fa9-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="69fa9-116">Procedimientos: Establecer el fondo de un panel</span><span class="sxs-lookup"><span data-stu-id="69fa9-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
