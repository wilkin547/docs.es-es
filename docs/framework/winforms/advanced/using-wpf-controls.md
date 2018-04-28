---
title: Utilizar controles WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8225447e6c0daa7894d622616131febb6ac82b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="using-wpf-controls"></a><span data-ttu-id="d3b7c-102">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="d3b7c-102">Using WPF Controls</span></span>
<span data-ttu-id="d3b7c-103">Puede usar controles de Windows Presentation Foundation (WPF) en las aplicaciones basadas en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="d3b7c-104">Aunque se trata de dos tecnologías de presentación diferentes, operan perfectamente entre sí.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="d3b7c-105">El Diseñador de Windows Forms proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="d3b7c-106">Un control WPF se hospeda un control de formularios Windows Forms especial que se denomina <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="d3b7c-107">Este control habilita el control WPF para participar en el diseño del formulario y recibir mensajes de teclado y mouse (ratón).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="d3b7c-108">En tiempo de diseño, puede organizar la <xref:System.Windows.Forms.Integration.ElementHost> controlar igual que lo haría con cualquier control de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="d3b7c-109">También puede usar controles de formularios Windows Forms en las aplicaciones basadas en WPF.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="d3b7c-110">Para obtener más información, consulte [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-110">For more information, see [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3b7c-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3b7c-111">In This Section</span></span>  
 [<span data-ttu-id="d3b7c-112">Copiar y pegar un control ElementHost en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d3b7c-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="d3b7c-113">Muestra cómo copiar un control de Windows Presentation Foundation en un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="d3b7c-114">Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d3b7c-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="d3b7c-115">Muestra cómo utilizar las características de diseño de formularios Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="d3b7c-116">Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d3b7c-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="d3b7c-117">Muestra el flujo de trabajo entre el Diseñador de Windows Forms y el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] para cambiar las propiedades de los controles WPF.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="d3b7c-118">Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d3b7c-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="d3b7c-119">Muestra cómo crear un control de Windows Presentation Foundation para su uso en las aplicaciones basadas en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="d3b7c-120">Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes</span><span class="sxs-lookup"><span data-stu-id="d3b7c-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="d3b7c-121">Muestra cómo copiar un control de Windows Presentation Foundation de un formulario Windows Forms a otro.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="d3b7c-122">Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d3b7c-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="d3b7c-123">Muestra cómo seleccionar los tipos de control de Windows Presentation Foundation que desea mostrar en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="d3b7c-124">Tutorial: Aplicar estilos al contenido de WPF</span><span class="sxs-lookup"><span data-stu-id="d3b7c-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="d3b7c-125">Muestra el flujo de trabajo entre el Diseñador de Windows Forms y la [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] para aplicar estilos a controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d3b7c-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="d3b7c-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="d3b7c-127">Describe una clase que puede utilizar para hospedar controles de Windows Presentation Foundation en las aplicaciones basadas en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="d3b7c-128">Describe una clase que puede utilizar para hospedar controles de formularios Windows Forms en una aplicación basada en Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3b7c-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d3b7c-129">Related Sections</span></span>  
 [<span data-ttu-id="d3b7c-130">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d3b7c-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="d3b7c-131">Describe la interoperabilidad entre las tecnologías de Windows Presentation Foundation y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="d3b7c-132">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="d3b7c-132">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="d3b7c-133">Describe cómo diseñar controles de Windows Presentation Foundation en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-133">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
