---
title: Utilizar controles WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211315"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="c79cf-102">Usar controles WPF</span><span class="sxs-lookup"><span data-stu-id="c79cf-102">Use WPF controls</span></span>

<span data-ttu-id="c79cf-103">Puede usar los controles de Windows Presentation Foundation (WPF) en sus aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c79cf-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="c79cf-104">Aunque son dos tecnologías de vista diferente, interoperan fácilmente.</span><span class="sxs-lookup"><span data-stu-id="c79cf-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="c79cf-105">El Diseñador de Windows Forms en Visual Studio proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c79cf-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="c79cf-106">Un control WPF se hospeda un control de Windows Forms especial que se denomina <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="c79cf-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="c79cf-107">Este control habilita el control WPF para participar en el diseño del formulario y recibir mensajes del teclado y mouse.</span><span class="sxs-lookup"><span data-stu-id="c79cf-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="c79cf-108">En tiempo de diseño, puede organizar la <xref:System.Windows.Forms.Integration.ElementHost> controlar tal como lo haría con cualquier control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c79cf-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="c79cf-109">También puede usar controles de formularios Windows Forms en sus aplicaciones basadas en WPF.</span><span class="sxs-lookup"><span data-stu-id="c79cf-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="c79cf-110">Para obtener más información, consulte [diseño XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c79cf-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c79cf-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c79cf-111">In This Section</span></span>

<span data-ttu-id="c79cf-112">[Cómo: Copiar y pegar un Control ElementHost en tiempo de diseño](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="c79cf-113">Se muestra cómo copiar un control de Windows Presentation Foundation en un formulario de Windows.</span><span class="sxs-lookup"><span data-stu-id="c79cf-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="c79cf-114">[Tutorial: Organizar el contenido WPF en Windows Forms en tiempo de diseño](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c79cf-115">Se muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c79cf-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="c79cf-116">[Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c79cf-117">Se muestra cómo crear un control de Windows Presentation Foundation para su uso en las aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c79cf-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="c79cf-118">[Tutorial: Asignar el contenido WPF en Windows Forms en tiempo de diseño](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c79cf-119">Muestra cómo seleccionar los tipos de control de Windows Presentation Foundation que desea mostrar en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c79cf-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="c79cf-120">[Tutorial: Aplicar estilos al contenido WPF](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="c79cf-121">Muestra el flujo de trabajo entre el Diseñador de Windows Forms y la [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] para aplicar estilos a controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c79cf-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="c79cf-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="c79cf-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="c79cf-123">Describe una clase que puede utilizar para hospedar controles de Windows Presentation Foundation en sus aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c79cf-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="c79cf-124">Describe una clase que puede usar para hospedar controles de Windows Forms en su aplicación basada en Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c79cf-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c79cf-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c79cf-125">Related sections</span></span>

<span data-ttu-id="c79cf-126">[Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="c79cf-127">Describe la interoperabilidad entre las tecnologías de Windows Presentation Foundation y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c79cf-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="c79cf-128">[Diseño XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="c79cf-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="c79cf-129">Describe cómo diseñar controles de Windows Presentation Foundation en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c79cf-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
