---
title: "Implementar el patrón de control Dock de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
caps.latest.revision: "23"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 68c3dcdb1d8f15f312dea40ae59a3b1a4736c484
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a><span data-ttu-id="4ac42-102">Implementar el patrón de control Dock de UI Automation</span><span class="sxs-lookup"><span data-stu-id="4ac42-102">Implementing the UI Automation Dock Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4ac42-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4ac42-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4ac42-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4ac42-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4ac42-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IDockProvider>y se incluye información sobre propiedades.</span><span class="sxs-lookup"><span data-stu-id="4ac42-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IDockProvider>, including information about properties.</span></span> <span data-ttu-id="4ac42-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="4ac42-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="4ac42-107">El patrón de control <xref:System.Windows.Automation.DockPattern> se utiliza para exponer las propiedades de acoplamiento de un control dentro de un contenedor de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="4ac42-107">The <xref:System.Windows.Automation.DockPattern> control pattern is used to expose the dock properties of a control within a docking container.</span></span> <span data-ttu-id="4ac42-108">Un contenedor de acoplamiento es un control que permite organizar elementos secundarios horizontal y verticalmente, relacionados entre sí.</span><span class="sxs-lookup"><span data-stu-id="4ac42-108">A docking container is a control that allows you to arrange child elements horizontally and vertically, relative to each other.</span></span> <span data-ttu-id="4ac42-109">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4ac42-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
 <span data-ttu-id="4ac42-110">![Acoplar contenedor con dos secundarios acoplados. ] (../../../docs/framework/ui-automation/media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span><span class="sxs-lookup"><span data-stu-id="4ac42-110">![Docking container with two docked children.](../../../docs/framework/ui-automation/media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span></span>  
<span data-ttu-id="4ac42-111">Ejemplo de acoplamiento de Visual Studio donde la ventana "Vista de clases" es DockPosition.Right y la ventana "Lista de errores" es DockPosition.Bottom</span><span class="sxs-lookup"><span data-stu-id="4ac42-111">Docking Example from Visual Studio Where "Class View" Window Is DockPosition.Right and "Error List" Window Is DockPosition.Bottom</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4ac42-112">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="4ac42-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4ac42-113">Al implementar el patrón de control Dock, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="4ac42-113">When implementing the Dock control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="4ac42-114"><xref:System.Windows.Automation.Provider.IDockProvider> no expone propiedades del contenedor de acoplamiento ni propiedades de controles que estén acoplados adyacentes al control actual dentro del contenedor de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="4ac42-114"><xref:System.Windows.Automation.Provider.IDockProvider> does not expose any properties of the docking container or any properties of controls that are docked adjacent to the current control within the docking container.</span></span>  
  
-   <span data-ttu-id="4ac42-115">Los controles se acoplan de forma relativa entre ellos, según su valor actual de orden Z; cuanto mayor es su ubicación de orden Z, más lejos se colocan del borde especificado del contenedor de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="4ac42-115">Controls are docked relative to each other based on their current z-order; the higher their z-order placement, the farther they are placed from the specified edge of the docking container.</span></span>  
  
-   <span data-ttu-id="4ac42-116">Si se cambia el tamaño del contenedor de acoplamiento, los controles acoplados dentro del contenedor cambiarán de posición y se alinearán con el mismo borde en el que estaban originalmente acoplados.</span><span class="sxs-lookup"><span data-stu-id="4ac42-116">If the docking container is resized, any docked controls within the container will be repositioned flush to the same edge to which they were originally docked.</span></span> <span data-ttu-id="4ac42-117">Los controles acoplados también cambiarán de tamaño para rellenar el espacio dentro del contenedor según el comportamiento de acoplamiento de sus elementos <xref:System.Windows.Automation.DockPosition>.</span><span class="sxs-lookup"><span data-stu-id="4ac42-117">The docked controls will also resize to fill any space within the container according to the docking behavior of their <xref:System.Windows.Automation.DockPosition>.</span></span> <span data-ttu-id="4ac42-118">Por ejemplo, si se especifica <xref:System.Windows.Automation.DockPosition.Top> , los lados izquierdo y derecho del control se expandirán para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="4ac42-118">For example, if <xref:System.Windows.Automation.DockPosition.Top> is specified, the left and right sides of the control will expand to fill any available space.</span></span> <span data-ttu-id="4ac42-119">Si se especifica <xref:System.Windows.Automation.DockPosition.Fill> , los cuatro lados del control se expandirán para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="4ac42-119">If <xref:System.Windows.Automation.DockPosition.Fill> is specified, all four sides of the control will expand to fill any available space.</span></span>  
  
-   <span data-ttu-id="4ac42-120">En un sistema de varios monitores, los controles se deben acoplar en el lado izquierdo o derecho del monitor actual.</span><span class="sxs-lookup"><span data-stu-id="4ac42-120">On a multi-monitor system, controls should dock to the left or right side of the current monitor.</span></span> <span data-ttu-id="4ac42-121">Si no es posible, deben acoplarse en el lado izquierdo del monitor que se encuentre más a la izquierda o en el lado derecho del monitor que se encuentre más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="4ac42-121">If that is not possible, they should dock to the left side of the leftmost monitor or the right side of the rightmost monitor.</span></span>  
  
<a name="Required_Members_for_IDockProvider"></a>   
## <a name="required-members-for-idockprovider"></a><span data-ttu-id="4ac42-122">Miembros requeridos para IDockProvider</span><span class="sxs-lookup"><span data-stu-id="4ac42-122">Required Members for IDockProvider</span></span>  
 <span data-ttu-id="4ac42-123">Se requieren los métodos y propiedades siguientes para implementar la interfaz de IDockProvider.</span><span class="sxs-lookup"><span data-stu-id="4ac42-123">The following properties and methods are required for implementing the IDockProvider interface.</span></span>  
  
|<span data-ttu-id="4ac42-124">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="4ac42-124">Required members</span></span>|<span data-ttu-id="4ac42-125">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="4ac42-125">Member type</span></span>|<span data-ttu-id="4ac42-126">Notas</span><span class="sxs-lookup"><span data-stu-id="4ac42-126">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|<span data-ttu-id="4ac42-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="4ac42-127">Property</span></span>|<span data-ttu-id="4ac42-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4ac42-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|<span data-ttu-id="4ac42-129">Método</span><span class="sxs-lookup"><span data-stu-id="4ac42-129">Method</span></span>|<span data-ttu-id="4ac42-130">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4ac42-130">None</span></span>|  
  
 <span data-ttu-id="4ac42-131">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="4ac42-131">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4ac42-132">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4ac42-132">Exceptions</span></span>  
 <span data-ttu-id="4ac42-133">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="4ac42-133">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="4ac42-134">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="4ac42-134">Exception type</span></span>|<span data-ttu-id="4ac42-135">Condición</span><span class="sxs-lookup"><span data-stu-id="4ac42-135">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> <span data-ttu-id="4ac42-136">-Cuando un control no es capaz de ejecutar el estilo de acoplamiento solicitado.</span><span class="sxs-lookup"><span data-stu-id="4ac42-136">-   When a control is not able to execute the requested dock style.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ac42-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ac42-137">See Also</span></span>  
 [<span data-ttu-id="4ac42-138">Información general del patrones de Control UI Automation</span><span class="sxs-lookup"><span data-stu-id="4ac42-138">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4ac42-139">Patrones de Control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="4ac42-139">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="4ac42-140">Patrones de Control UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="4ac42-140">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="4ac42-141">Información general sobre el árbol de automatización de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4ac42-141">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="4ac42-142">Usar almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="4ac42-142">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
