---
title: Implementar el patrón de control GridItem de UI Automation
description: Conozca las directrices y convenciones para implementar el patrón de control GridItemPattern para los elementos de cuadrícula en la automatización de la interfaz de usuario. Consulte los miembros necesarios para IGridItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: 30932e630c663aabb7d26302174785d44dc1c385
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267889"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="8992d-104">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-104">Implementing the UI Automation GridItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="8992d-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8992d-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8992d-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8992d-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8992d-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>y se incluye información sobre propiedades.</span><span class="sxs-lookup"><span data-stu-id="8992d-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="8992d-108">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="8992d-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="8992d-109">El patrón de control <xref:System.Windows.Automation.GridItemPattern> se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="8992d-109">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="8992d-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8992d-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="8992d-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="8992d-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="8992d-112">Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las directrices y convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8992d-112">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="8992d-113">Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).</span><span class="sxs-lookup"><span data-stu-id="8992d-113">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="8992d-114">Las celdas combinadas informarán de sus propiedades <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> según su celda de anclaje subyacente, como define el proveedor de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8992d-114">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="8992d-115">Normalmente, será la fila o columna superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="8992d-115">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="8992d-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> no permite la manipulación activa de la cuadrícula, como la combinación o la división de celdas.</span><span class="sxs-lookup"><span data-stu-id="8992d-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="8992d-117">Los controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> normalmente se pueden atravesar (es decir, un cliente de UI Automation puede moverse a los controles adyacentes) con el teclado.</span><span class="sxs-lookup"><span data-stu-id="8992d-117">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>

## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="8992d-118">Miembros requeridos para IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="8992d-118">Required Members for IGridItemProvider</span></span>  

 <span data-ttu-id="8992d-119">Para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="8992d-119">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="8992d-120">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="8992d-120">Required members</span></span>|<span data-ttu-id="8992d-121">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="8992d-121">Member type</span></span>|<span data-ttu-id="8992d-122">Notas</span><span class="sxs-lookup"><span data-stu-id="8992d-122">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="8992d-123">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8992d-123">Property</span></span>|<span data-ttu-id="8992d-124">None</span><span class="sxs-lookup"><span data-stu-id="8992d-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="8992d-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8992d-125">Property</span></span>|<span data-ttu-id="8992d-126">None</span><span class="sxs-lookup"><span data-stu-id="8992d-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="8992d-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8992d-127">Property</span></span>|<span data-ttu-id="8992d-128">None</span><span class="sxs-lookup"><span data-stu-id="8992d-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="8992d-129">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8992d-129">Property</span></span>|<span data-ttu-id="8992d-130">None</span><span class="sxs-lookup"><span data-stu-id="8992d-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="8992d-131">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8992d-131">Property</span></span>|<span data-ttu-id="8992d-132">None</span><span class="sxs-lookup"><span data-stu-id="8992d-132">None</span></span>|  
  
 <span data-ttu-id="8992d-133">Este patrón de control no tiene métodos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="8992d-133">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="8992d-134">Excepciones</span><span class="sxs-lookup"><span data-stu-id="8992d-134">Exceptions</span></span>  

 <span data-ttu-id="8992d-135">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="8992d-135">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8992d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8992d-136">See also</span></span>

- [<span data-ttu-id="8992d-137">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="8992d-138">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="8992d-139">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="8992d-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="8992d-140">Implementar el patrón de control Grid de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-140">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="8992d-141">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-141">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="8992d-142">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="8992d-142">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
