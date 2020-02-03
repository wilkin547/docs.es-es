---
title: para controles de anclado
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747179"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="89422-102">Cómo: delimitar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89422-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="89422-103">Si está diseñando un formulario que el usuario puede cambiar de tamaño en tiempo de ejecución, los controles del formulario deben cambiar de tamaño y de posición correctamente.</span><span class="sxs-lookup"><span data-stu-id="89422-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="89422-104">Para cambiar el tamaño de los controles dinámicamente con el formulario, puede usar la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> de los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="89422-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="89422-105">La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> define una posición de delimitador para el control.</span><span class="sxs-lookup"><span data-stu-id="89422-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="89422-106">Cuando un control se delimita en un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de delimitador.</span><span class="sxs-lookup"><span data-stu-id="89422-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="89422-107">Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> que está anclado a los bordes izquierdo, derecho e inferior del formulario, a medida que se cambia el tamaño del formulario, el control <xref:System.Windows.Forms.TextBox> cambia de tamaño horizontalmente para mantener la misma distancia desde los lados derecho e izquierdo del formulario.</span><span class="sxs-lookup"><span data-stu-id="89422-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="89422-108">Además, el control se coloca verticalmente de forma que su ubicación siempre sea la misma distancia del borde inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="89422-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="89422-109">Si un control no está delimitado y se cambia el tamaño del formulario, se cambia la posición del control con respecto a los bordes del formulario.</span><span class="sxs-lookup"><span data-stu-id="89422-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="89422-110">La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="89422-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="89422-111">Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="89422-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="89422-112">Delimitar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="89422-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="89422-113">En Visual Studio, seleccione el control que quiere delimitar.</span><span class="sxs-lookup"><span data-stu-id="89422-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="89422-114">Para delimitar varios controles simultáneamente, presione la tecla CTRL, haga clic en cada control para seleccionarlo y, a continuación, siga el resto de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89422-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="89422-115">En la ventana **propiedades** , haga clic en la flecha situada a la derecha de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="89422-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="89422-116">Se muestra un editor que muestra una cruz.</span><span class="sxs-lookup"><span data-stu-id="89422-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="89422-117">Para establecer un delimitador, haga clic en la sección superior, izquierda, derecha o inferior de la Cruz.</span><span class="sxs-lookup"><span data-stu-id="89422-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="89422-118">Los controles se delimitan a la parte superior e izquierda de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89422-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="89422-119">Para borrar un lado del control que se ha anclado, haga clic en ese brazo de la Cruz.</span><span class="sxs-lookup"><span data-stu-id="89422-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="89422-120">Para cerrar el editor de propiedades de <xref:System.Windows.Forms.Control.Anchor%2A>, vuelva a hacer clic en el nombre de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="89422-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="89422-121">Cuando se muestra el formulario en tiempo de ejecución, el control cambia de tamaño para permanecer colocado a la misma distancia del borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="89422-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="89422-122">La distancia desde el borde delimitado siempre permanece igual que la distancia definida cuando el control se coloca en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="89422-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="89422-123">Algunos controles, como el control <xref:System.Windows.Forms.ComboBox>, tienen un límite de alto.</span><span class="sxs-lookup"><span data-stu-id="89422-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="89422-124">Al delimitar el control a la parte inferior de su formulario o contenedor no se puede forzar que el control supere su límite de alto.</span><span class="sxs-lookup"><span data-stu-id="89422-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="89422-125">Los controles heredados deben estar `Protected` para poder ser delimitados.</span><span class="sxs-lookup"><span data-stu-id="89422-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="89422-126">Para cambiar el nivel de acceso de un control, establezca su propiedad `Modifiers` en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="89422-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="89422-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89422-127">See also</span></span>

- [<span data-ttu-id="89422-128">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89422-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="89422-129">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="89422-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="89422-130">Procedimiento para acoplar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89422-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="89422-131">Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="89422-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="89422-132">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="89422-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="89422-133">Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="89422-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
