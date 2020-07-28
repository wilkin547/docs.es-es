---
title: Implementar el patrón de control ScrollItem de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control ScrollItem en la automatización de la interfaz de usuario. Consulte los miembros necesarios para la interfaz IScrollItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: a548eb25280d9a8feddc4633a1ba3e7dc022af36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163571"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="2fe91-104">Implementar el patrón de control ScrollItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="2fe91-104">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="2fe91-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="2fe91-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2fe91-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="2fe91-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2fe91-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IScrollItemProvider>, incluida la información sobre propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="2fe91-107">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="2fe91-108">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="2fe91-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="2fe91-109">El patrón de control <xref:System.Windows.Automation.ScrollItemPattern> se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="2fe91-109">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="2fe91-110">Este patrón de control actúa como canal de comunicación entre un control secundario y su contenedor para garantizar que el contenedor puede cambiar el contenido (o región) visible en ese momento dentro de su ventanilla para mostrar el control secundario.</span><span class="sxs-lookup"><span data-stu-id="2fe91-110">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="2fe91-111">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2fe91-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2fe91-112">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="2fe91-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="2fe91-113">Al implementar el patrón de control Scroll Item, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="2fe91-113">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="2fe91-114">Los elementos que se incluye en un control Window o Canvas no tienen que implementar la interfaz de IScrollItemProvider.</span><span class="sxs-lookup"><span data-stu-id="2fe91-114">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="2fe91-115">Sin embargo, como alternativa, deben exponer una ubicación válida para <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="2fe91-115">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="2fe91-116">Esto permitirá que una aplicación cliente de UI Automation use los métodos de patrón de control <xref:System.Windows.Automation.ScrollPattern> en el contenedor para que muestre el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="2fe91-116">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="2fe91-117">Miembros requeridos para IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="2fe91-117">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="2fe91-118">El siguiente método es necesario para implementar la interfaz de IScrollProvider.</span><span class="sxs-lookup"><span data-stu-id="2fe91-118">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="2fe91-119">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="2fe91-119">Required members</span></span>|<span data-ttu-id="2fe91-120">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="2fe91-120">Member type</span></span>|<span data-ttu-id="2fe91-121">Notas</span><span class="sxs-lookup"><span data-stu-id="2fe91-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="2fe91-122">-(Método)</span><span class="sxs-lookup"><span data-stu-id="2fe91-122">-   Method</span></span>|<span data-ttu-id="2fe91-123">None</span><span class="sxs-lookup"><span data-stu-id="2fe91-123">None</span></span>|  
  
 <span data-ttu-id="2fe91-124">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="2fe91-124">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="2fe91-125">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2fe91-125">Exceptions</span></span>  
 <span data-ttu-id="2fe91-126">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="2fe91-126">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="2fe91-127">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="2fe91-127">Exception Type</span></span>|<span data-ttu-id="2fe91-128">Condición</span><span class="sxs-lookup"><span data-stu-id="2fe91-128">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="2fe91-129">Si no se puede desplazar un elemento en la vista:</span><span class="sxs-lookup"><span data-stu-id="2fe91-129">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="2fe91-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fe91-130">See also</span></span>

- [<span data-ttu-id="2fe91-131">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="2fe91-131">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="2fe91-132">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="2fe91-132">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="2fe91-133">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="2fe91-133">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="2fe91-134">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="2fe91-134">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="2fe91-135">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="2fe91-135">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
