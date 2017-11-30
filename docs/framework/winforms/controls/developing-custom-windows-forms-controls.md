---
title: Desarrollar controles personalizados de formularios Windows Forms con .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89be7e347556c8ec34296044f17fbfd4450bc127
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="fe622-102">Desarrollar controles personalizados de formularios Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fe622-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="fe622-103">Los controles de Windows Forms son componentes reutilizables que encapsulan la funcionalidad de la interfaz de usuario y se usan en aplicaciones de cliente basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="fe622-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="fe622-104">Windows Forms no solo ofrece muchos controles listos para usar, también proporciona la infraestructura para desarrollar sus propios controles.</span><span class="sxs-lookup"><span data-stu-id="fe622-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="fe622-105">Puede combinar los controles existentes, ampliar los controles existentes o crear sus propios controles personalizados.</span><span class="sxs-lookup"><span data-stu-id="fe622-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="fe622-106">En esta sección se ofrece información general y ejemplos que le ayudarán a desarrollar controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fe622-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe622-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fe622-107">In This Section</span></span>  
 <span data-ttu-id="fe622-108">[Overview of Using Controls in Windows Forms](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md) (Información general sobre cómo utilizar controles en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fe622-108">[Overview of Using Controls in Windows Forms](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)</span></span>  
 <span data-ttu-id="fe622-109">Destaca los elementos básicos del uso de controles en aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fe622-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="fe622-110">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="fe622-110">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="fe622-111">Describe los diferentes tipos de controles personalizados que puede crear con el espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe622-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="fe622-112">Fundamentos de desarrollo de controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe622-112">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 <span data-ttu-id="fe622-113">Describe los primeros pasos para desarrollar un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fe622-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="fe622-114">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe622-114">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 <span data-ttu-id="fe622-115">Muestra cómo agregar propiedades a controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fe622-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="fe622-116">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe622-116">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 <span data-ttu-id="fe622-117">Muestra cómo controlar y definir eventos en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fe622-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="fe622-118">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe622-118">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="fe622-119">Describe los atributos que se puede aplicar a propiedades u otros miembros de los controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="fe622-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="fe622-120">[Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md) (Pintura y representación personalizadas de controles)</span><span class="sxs-lookup"><span data-stu-id="fe622-120">[Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)</span></span>  
 <span data-ttu-id="fe622-121">Muestra cómo personalizar la apariencia de los controles.</span><span class="sxs-lookup"><span data-stu-id="fe622-121">Shows how to customize the appearance of your controls.</span></span>  
  
 <span data-ttu-id="fe622-122">[Layout in Windows Forms Controls](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md) (Diseño en controles de Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fe622-122">[Layout in Windows Forms Controls](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)</span></span>  
 <span data-ttu-id="fe622-123">Muestra cómo crear diseños sofisticados para los controles y formularios.</span><span class="sxs-lookup"><span data-stu-id="fe622-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 <span data-ttu-id="fe622-124">[Multithreading in Windows Forms Controls](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md) (Multithreading en controles de Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fe622-124">[Multithreading in Windows Forms Controls](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)</span></span>  
 <span data-ttu-id="fe622-125">Muestra cómo implementar controles multiproceso.</span><span class="sxs-lookup"><span data-stu-id="fe622-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fe622-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="fe622-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="fe622-127">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="fe622-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="fe622-128">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="fe622-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fe622-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe622-129">Related Sections</span></span>  
 [<span data-ttu-id="fe622-130">Atributos en tiempo de diseño para componentes</span><span class="sxs-lookup"><span data-stu-id="fe622-130">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="fe622-131">Enumera los atributos de metadatos que se deben aplicar a componentes y controles para que se muestren correctamente en tiempo de diseño en diseñadores visuales.</span><span class="sxs-lookup"><span data-stu-id="fe622-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="fe622-132">Ampliar compatibilidad en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="fe622-132">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="fe622-133">Describe cómo implementar clases, como editores y diseñadores, que proporcionan compatibilidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="fe622-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 [<span data-ttu-id="fe622-134">Cómo: Obtener licencia para componentes y controles</span><span class="sxs-lookup"><span data-stu-id="fe622-134">How to: License Components and Controls</span></span>](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 <span data-ttu-id="fe622-135">Describe cómo se implementan las licencias en el control o componente.</span><span class="sxs-lookup"><span data-stu-id="fe622-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="fe622-136">Vea también [Desarrollar controles de Windows Forms en tiempo de diseño](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fe622-136">Also see [Developing Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span></span>
