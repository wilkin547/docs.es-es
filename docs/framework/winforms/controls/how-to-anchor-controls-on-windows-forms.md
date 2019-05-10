---
title: Procedimiento para delimitar controles en formularios Windows Forms
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
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211274"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="1da2c-102">Procedimiento para delimitar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1da2c-102">How to: Anchor Controls on Windows Forms</span></span>

<span data-ttu-id="1da2c-103">Si va a diseñar un formulario que el usuario puede cambiar el tamaño en tiempo de ejecución, deben cambiar el tamaño de los controles en el formulario y la posición de correctamente.</span><span class="sxs-lookup"><span data-stu-id="1da2c-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="1da2c-104">Para cambiar el tamaño de controles dinámicamente con el formulario, puede usar el <xref:System.Windows.Forms.Control.Anchor%2A> propiedades de controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1da2c-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="1da2c-105">El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad define una posición de delimitación para el control.</span><span class="sxs-lookup"><span data-stu-id="1da2c-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="1da2c-106">Cuando un control se acopla a un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de anclaje.</span><span class="sxs-lookup"><span data-stu-id="1da2c-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="1da2c-107">Por ejemplo, si tiene un <xref:System.Windows.Forms.TextBox> control que está anclada a la izquierda, derecha y los bordes de la parte inferior del formulario, como el tamaño del formulario, el <xref:System.Windows.Forms.TextBox> control cambia automáticamente de tamaño horizontalmente para que mantiene la misma distancia desde los lados derecho e izquierdos del formulario.</span><span class="sxs-lookup"><span data-stu-id="1da2c-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="1da2c-108">Además, el control se coloca verticalmente para que su ubicación es siempre la misma distancia desde el borde inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="1da2c-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="1da2c-109">Si no se encuentra delimitado respecto de un control y se cambia el tamaño del formulario, se cambia la posición del control en relación con los bordes del formulario.</span><span class="sxs-lookup"><span data-stu-id="1da2c-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="1da2c-110">El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1da2c-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="1da2c-111">Para obtener más información, consulte [AutoSize Property Overview](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1da2c-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="1da2c-112">Anclar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="1da2c-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="1da2c-113">En Visual Studio, seleccione el control que desee anclar.</span><span class="sxs-lookup"><span data-stu-id="1da2c-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1da2c-114">Puede delimitar varios controles simultáneamente al presionar la tecla CTRL, haciendo clic en cada control para seleccionarlo y, a continuación, siga el resto de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1da2c-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="1da2c-115">En el **propiedades** ventana, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Anchor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1da2c-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="1da2c-116">Se muestra un editor que se muestra una cruz.</span><span class="sxs-lookup"><span data-stu-id="1da2c-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="1da2c-117">Para establecer un delimitador, haga clic en la parte superior, izquierda, derecha o la sección inferior de la cruz.</span><span class="sxs-lookup"><span data-stu-id="1da2c-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="1da2c-118">Los controles se fija con respecto a la parte superior y deja de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1da2c-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="1da2c-119">Para borrar un lado del control delimitado, haga clic en esa rama de la cruz.</span><span class="sxs-lookup"><span data-stu-id="1da2c-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="1da2c-120">Para cerrar el <xref:System.Windows.Forms.Control.Anchor%2A> editor de propiedades, haga clic en el <xref:System.Windows.Forms.Control.Anchor%2A> nuevo nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1da2c-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="1da2c-121">Cuando se muestre el formulario en tiempo de ejecución, el control cambia de tamaño para permanecer ubicado a la misma distancia desde el borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="1da2c-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="1da2c-122">La distancia desde el borde delimitado siempre permanece igual la distancia definida cuando se coloca el control en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1da2c-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="1da2c-123">Ciertos controles, como el <xref:System.Windows.Forms.ComboBox> controlar, tienen un límite de su alto.</span><span class="sxs-lookup"><span data-stu-id="1da2c-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="1da2c-124">Delimitar el control a la parte inferior de su formulario o contenedor, no puede forzar el control a superar su límite de alto.</span><span class="sxs-lookup"><span data-stu-id="1da2c-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="1da2c-125">Los controles heredados deben estar `Protected` para poder ser delimitados.</span><span class="sxs-lookup"><span data-stu-id="1da2c-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="1da2c-126">Para cambiar el nivel de acceso de un control, establezca su `Modifiers` propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="1da2c-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="1da2c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1da2c-127">See also</span></span>

- [<span data-ttu-id="1da2c-128">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1da2c-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="1da2c-129">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1da2c-129">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="1da2c-130">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="1da2c-130">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="1da2c-131">Cómo: Acoplar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1da2c-131">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="1da2c-132">Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1da2c-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="1da2c-133">Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1da2c-133">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="1da2c-134">Tutorial: Diseñar Windows controles Forms con relleno, márgenes y la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="1da2c-134">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
