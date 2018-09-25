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
ms.openlocfilehash: 68de80e4a01de27c16c0ed85c4177c562d5e328b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089953"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="c7e6d-102">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="c7e6d-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="c7e6d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c7e6d-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="c7e6d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c7e6d-105">En este tema se presenta las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, incluida información acerca de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="c7e6d-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="c7e6d-107">El <xref:System.Windows.Automation.GridItemPattern> patrón de control se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="c7e6d-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c7e6d-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="c7e6d-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="c7e6d-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="c7e6d-110">Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="c7e6d-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="c7e6d-111">Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).</span><span class="sxs-lookup"><span data-stu-id="c7e6d-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="c7e6d-112">Las celdas combinadas informarán de sus propiedades <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> según su celda de anclaje subyacente, como define el proveedor de UI Automation.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="c7e6d-113">Normalmente, será la fila o columna superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="c7e6d-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> no se proporciona para la manipulación activa de la cuadrícula, como la combinación o división de celdas.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="c7e6d-115">Los controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> normalmente se pueden atravesar (es decir, un cliente de UI Automation puede moverse a los controles adyacentes) con el teclado.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="c7e6d-116">Miembros requeridos para IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="c7e6d-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="c7e6d-117">Para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="c7e6d-118">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="c7e6d-118">Required members</span></span>|<span data-ttu-id="c7e6d-119">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="c7e6d-119">Member type</span></span>|<span data-ttu-id="c7e6d-120">Notas</span><span class="sxs-lookup"><span data-stu-id="c7e6d-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="c7e6d-121">Property</span><span class="sxs-lookup"><span data-stu-id="c7e6d-121">Property</span></span>|<span data-ttu-id="c7e6d-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7e6d-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="c7e6d-123">Property</span><span class="sxs-lookup"><span data-stu-id="c7e6d-123">Property</span></span>|<span data-ttu-id="c7e6d-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7e6d-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="c7e6d-125">Property</span><span class="sxs-lookup"><span data-stu-id="c7e6d-125">Property</span></span>|<span data-ttu-id="c7e6d-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7e6d-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="c7e6d-127">Property</span><span class="sxs-lookup"><span data-stu-id="c7e6d-127">Property</span></span>|<span data-ttu-id="c7e6d-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7e6d-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="c7e6d-129">Property</span><span class="sxs-lookup"><span data-stu-id="c7e6d-129">Property</span></span>|<span data-ttu-id="c7e6d-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c7e6d-130">None</span></span>|  
  
 <span data-ttu-id="c7e6d-131">Este patrón de control no tiene métodos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="c7e6d-132">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c7e6d-132">Exceptions</span></span>  
 <span data-ttu-id="c7e6d-133">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e6d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7e6d-134">See Also</span></span>  
 [<span data-ttu-id="c7e6d-135">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7e6d-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="c7e6d-136">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7e6d-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="c7e6d-137">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="c7e6d-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="c7e6d-138">Implementación del patrón de control Grid de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7e6d-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="c7e6d-139">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7e6d-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="c7e6d-140">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7e6d-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
