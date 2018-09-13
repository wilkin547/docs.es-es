---
title: Implementar el patrón de control ScrollItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0346b70b4400c5f7a8d282d945e029701973dad1
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44707976"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="f2fd9-102">Implementar el patrón de control ScrollItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f2fd9-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="f2fd9-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f2fd9-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f2fd9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f2fd9-105">En este tema se presenta las directrices y convenciones para implementar el <xref:System.Windows.Automation.Provider.IScrollItemProvider>, incluida la información sobre las propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="f2fd9-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="f2fd9-107">El <xref:System.Windows.Automation.ScrollItemPattern> patrón de control se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="f2fd9-108">Este patrón de control actúa como canal de comunicación entre un control secundario y su contenedor para garantizar que el contenedor puede cambiar el contenido (o región) visible en ese momento dentro de su ventanilla para mostrar el control secundario.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="f2fd9-109">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f2fd9-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f2fd9-110">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="f2fd9-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f2fd9-111">Al implementar el patrón de control Scroll Item, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="f2fd9-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="f2fd9-112">Los elementos que se incluye en un control Window o Canvas no tienen que implementar la interfaz de IScrollItemProvider.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="f2fd9-113">Como alternativa, sin embargo, debe exponer una ubicación válida para el <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="f2fd9-114">Esto permitirá que una aplicación cliente de UI Automation use los métodos de patrón de control <xref:System.Windows.Automation.ScrollPattern> en el contenedor para que muestre el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="f2fd9-115">Miembros requeridos para IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="f2fd9-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="f2fd9-116">El siguiente método es necesario para implementar la interfaz de IScrollProvider.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="f2fd9-117">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="f2fd9-117">Required members</span></span>|<span data-ttu-id="f2fd9-118">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="f2fd9-118">Member type</span></span>|<span data-ttu-id="f2fd9-119">Notas</span><span class="sxs-lookup"><span data-stu-id="f2fd9-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="f2fd9-120">-Método</span><span class="sxs-lookup"><span data-stu-id="f2fd9-120">-   Method</span></span>|<span data-ttu-id="f2fd9-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f2fd9-121">None</span></span>|  
  
 <span data-ttu-id="f2fd9-122">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="f2fd9-123">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f2fd9-123">Exceptions</span></span>  
 <span data-ttu-id="f2fd9-124">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="f2fd9-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="f2fd9-125">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="f2fd9-125">Exception Type</span></span>|<span data-ttu-id="f2fd9-126">Condición</span><span class="sxs-lookup"><span data-stu-id="f2fd9-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="f2fd9-127">Si no se puede desplazar un elemento en la vista:</span><span class="sxs-lookup"><span data-stu-id="f2fd9-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="f2fd9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2fd9-128">See Also</span></span>  
 [<span data-ttu-id="f2fd9-129">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f2fd9-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="f2fd9-130">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f2fd9-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="f2fd9-131">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="f2fd9-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="f2fd9-132">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f2fd9-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="f2fd9-133">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f2fd9-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
