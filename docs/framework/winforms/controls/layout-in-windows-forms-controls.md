---
title: Diseño de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: d1a3954c8eda87bdda9fa17df1bd2b3858c43619
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012833"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="b5f32-102">Diseño de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5f32-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="b5f32-103">La posición precisa de los controles del formulario es de alta prioridad para muchas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b5f32-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="b5f32-104">El <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres le ofrece muchas herramientas de diseño para realizar esta acción.</span><span class="sxs-lookup"><span data-stu-id="b5f32-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b5f32-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b5f32-105">In This Section</span></span>

<span data-ttu-id="b5f32-106">[Información general de la propiedad AutoSize](autosize-property-overview.md)\\</span><span class="sxs-lookup"><span data-stu-id="b5f32-106">[AutoSize Property Overview](autosize-property-overview.md)\\</span></span>
<span data-ttu-id="b5f32-107">Describe el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad y su función en el diseño.</span><span class="sxs-lookup"><span data-stu-id="b5f32-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="b5f32-108">[Márgenes y relleno en Windows Forms, controles](margin-and-padding-in-windows-forms-controls.md)\\</span><span class="sxs-lookup"><span data-stu-id="b5f32-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)\\</span></span>
<span data-ttu-id="b5f32-109">Describe el <xref:System.Windows.Forms.Control.Margin%2A> y <xref:System.Windows.Forms.Control.Padding%2A> propiedades y sus funciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="b5f32-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="b5f32-110">[Cómo: Alinear un Control con los bordes de formularios](how-to-align-a-control-to-the-edges-of-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b5f32-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)\\</span></span>
<span data-ttu-id="b5f32-111">Muestra cómo usar el <xref:System.Windows.Forms.Control.Dock%2A> propiedad para alinear el control con el borde del formulario que ocupa.</span><span class="sxs-lookup"><span data-stu-id="b5f32-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="b5f32-112">[Cómo: Crear un borde alrededor de un formulario Windows Forms con relleno de Control](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span><span class="sxs-lookup"><span data-stu-id="b5f32-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span></span>
<span data-ttu-id="b5f32-113">Muestra cómo usar el <xref:System.Windows.Forms.Control.Padding%2A> propiedad para describir un control.</span><span class="sxs-lookup"><span data-stu-id="b5f32-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="b5f32-114">[Cómo: Implementar un motor de diseño personalizado](how-to-implement-a-custom-layout-engine.md)\\</span><span class="sxs-lookup"><span data-stu-id="b5f32-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)\\</span></span>
<span data-ttu-id="b5f32-115">Muestra cómo implementar un <xref:System.Windows.Forms.Layout.LayoutEngine> para organizar los controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b5f32-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="b5f32-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="b5f32-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="b5f32-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b5f32-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="b5f32-118">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b5f32-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5f32-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5f32-119">See also</span></span>

- [<span data-ttu-id="b5f32-120">Cómo: Delimitar y acoplar controles secundarios en un Control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b5f32-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="b5f32-121">Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b5f32-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="b5f32-122">Cómo: Crear un diseño de formularios de Windows que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="b5f32-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="b5f32-123">Comportamiento de AutoSize en el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b5f32-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
