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
ms.openlocfilehash: b5550aef220ece09d5486421275b19a37bfe9011
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329783"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="a5154-102">Procedimiento para delimitar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5154-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="a5154-103">Si está diseñando un formulario que el usuario puede cambiar el tamaño en tiempo de ejecución, deben cambiar el tamaño de los controles en el formulario y la posición de correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5154-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="a5154-104">Para cambiar el tamaño de controles dinámicamente con el formulario, puede usar el <xref:System.Windows.Forms.Control.Anchor%2A> propiedades de controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5154-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="a5154-105">El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad define una posición de delimitación para el control.</span><span class="sxs-lookup"><span data-stu-id="a5154-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="a5154-106">Cuando un control se acopla a un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de anclaje.</span><span class="sxs-lookup"><span data-stu-id="a5154-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="a5154-107">Por ejemplo, si tiene un <xref:System.Windows.Forms.TextBox> control que está anclada a la izquierda, derecha y los bordes de la parte inferior del formulario, como el tamaño del formulario, el <xref:System.Windows.Forms.TextBox> control cambia automáticamente de tamaño horizontalmente para que mantiene la misma distancia desde los lados derecho e izquierdos del formulario.</span><span class="sxs-lookup"><span data-stu-id="a5154-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="a5154-108">Además, el control se coloca verticalmente para que su ubicación es siempre la misma distancia desde el borde inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="a5154-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="a5154-109">Si no se encuentra delimitado respecto de un control y se cambia el tamaño del formulario, se cambia la posición del control en relación con los bordes del formulario.</span><span class="sxs-lookup"><span data-stu-id="a5154-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="a5154-110">El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a5154-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="a5154-111">Para obtener más información, consulte [AutoSize Property Overview](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5154-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5154-112">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="a5154-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a5154-113">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="a5154-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a5154-114">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a5154-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="a5154-115">Para anclar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="a5154-115">To anchor a control on a form</span></span>  
  
1. <span data-ttu-id="a5154-116">Seleccione el control que desee anclar.</span><span class="sxs-lookup"><span data-stu-id="a5154-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5154-117">Puede delimitar varios controles simultáneamente al presionar la tecla CTRL, haciendo clic en cada control para seleccionarlo y, a continuación, siga el resto de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a5154-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2. <span data-ttu-id="a5154-118">En el **propiedades** ventana, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Anchor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a5154-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="a5154-119">Se muestra un editor que se muestra una cruz.</span><span class="sxs-lookup"><span data-stu-id="a5154-119">An editor is displayed that shows a cross.</span></span>  
  
3. <span data-ttu-id="a5154-120">Para establecer un delimitador, haga clic en la parte superior, izquierda, derecha o la sección inferior de la cruz.</span><span class="sxs-lookup"><span data-stu-id="a5154-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="a5154-121">Los controles se fija con respecto a la parte superior y deja de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5154-121">Controls are anchored to the top and left by default.</span></span>  
  
4. <span data-ttu-id="a5154-122">Para borrar un lado del control delimitado, haga clic en esa rama de la cruz.</span><span class="sxs-lookup"><span data-stu-id="a5154-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5. <span data-ttu-id="a5154-123">Para cerrar el <xref:System.Windows.Forms.Control.Anchor%2A> editor de propiedades, haga clic en el <xref:System.Windows.Forms.Control.Anchor%2A> nuevo nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a5154-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="a5154-124">Cuando se muestre el formulario en tiempo de ejecución, el control cambia de tamaño para permanecer ubicado a la misma distancia desde el borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="a5154-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="a5154-125">La distancia desde el borde delimitado siempre permanece igual la distancia definida cuando se coloca el control en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5154-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5154-126">Ciertos controles, como el <xref:System.Windows.Forms.ComboBox> controlar, tienen un límite de su alto.</span><span class="sxs-lookup"><span data-stu-id="a5154-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="a5154-127">Delimitar el control a la parte inferior de su formulario o contenedor, no puede forzar el control a superar su límite de alto.</span><span class="sxs-lookup"><span data-stu-id="a5154-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="a5154-128">Los controles heredados deben estar `Protected` para poder ser delimitados.</span><span class="sxs-lookup"><span data-stu-id="a5154-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="a5154-129">Para cambiar el nivel de acceso de un control, establezca su `Modifiers` propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="a5154-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5154-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5154-130">See also</span></span>

- [<span data-ttu-id="a5154-131">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5154-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="a5154-132">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5154-132">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="a5154-133">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="a5154-133">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="a5154-134">Cómo: Acoplar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5154-134">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="a5154-135">Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a5154-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="a5154-136">Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a5154-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="a5154-137">Tutorial: Diseñar Windows controles Forms con relleno, márgenes y la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="a5154-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
