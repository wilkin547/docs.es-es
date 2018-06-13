---
title: Implementar el patrón de control GridItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: bfe7fb8ab64f148d8ca5af0e419ca60690a1acce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408293"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="f296e-102">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f296e-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="f296e-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f296e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f296e-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f296e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f296e-105">En este tema se presenta las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, incluida la información acerca de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f296e-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="f296e-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="f296e-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="f296e-107">El <xref:System.Windows.Automation.GridItemPattern> patrón de control se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="f296e-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="f296e-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f296e-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f296e-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="f296e-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f296e-110">Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las directrices y convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f296e-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="f296e-111">Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).</span><span class="sxs-lookup"><span data-stu-id="f296e-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="f296e-112">Las celdas combinadas informarán de sus propiedades <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> según su celda de anclaje subyacente, como define el proveedor de UI Automation.</span><span class="sxs-lookup"><span data-stu-id="f296e-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="f296e-113">Normalmente, será la fila o columna superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="f296e-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="f296e-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> no se proporciona para la manipulación activa de la cuadrícula, como la combinación o la división de celdas.</span><span class="sxs-lookup"><span data-stu-id="f296e-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="f296e-115">Los controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> normalmente se pueden atravesar (es decir, un cliente de UI Automation puede moverse a los controles adyacentes) con el teclado.</span><span class="sxs-lookup"><span data-stu-id="f296e-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="f296e-116">Miembros requeridos para IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="f296e-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="f296e-117">Para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="f296e-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="f296e-118">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="f296e-118">Required members</span></span>|<span data-ttu-id="f296e-119">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="f296e-119">Member type</span></span>|<span data-ttu-id="f296e-120">Notas</span><span class="sxs-lookup"><span data-stu-id="f296e-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="f296e-121">Property</span><span class="sxs-lookup"><span data-stu-id="f296e-121">Property</span></span>|<span data-ttu-id="f296e-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f296e-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="f296e-123">Property</span><span class="sxs-lookup"><span data-stu-id="f296e-123">Property</span></span>|<span data-ttu-id="f296e-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f296e-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="f296e-125">Property</span><span class="sxs-lookup"><span data-stu-id="f296e-125">Property</span></span>|<span data-ttu-id="f296e-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f296e-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="f296e-127">Property</span><span class="sxs-lookup"><span data-stu-id="f296e-127">Property</span></span>|<span data-ttu-id="f296e-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f296e-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="f296e-129">Property</span><span class="sxs-lookup"><span data-stu-id="f296e-129">Property</span></span>|<span data-ttu-id="f296e-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f296e-130">None</span></span>|  
  
 <span data-ttu-id="f296e-131">Este patrón de control no tiene métodos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="f296e-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="f296e-132">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f296e-132">Exceptions</span></span>  
 <span data-ttu-id="f296e-133">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="f296e-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f296e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f296e-134">See Also</span></span>  
 [<span data-ttu-id="f296e-135">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f296e-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="f296e-136">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f296e-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="f296e-137">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="f296e-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="f296e-138">Implementación del patrón de control Grid de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f296e-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="f296e-139">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f296e-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="f296e-140">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f296e-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
