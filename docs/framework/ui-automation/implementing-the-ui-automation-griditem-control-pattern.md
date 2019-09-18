---
title: Implementar el patrón de control GridItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: fdaac3cad61f6047201587e48d4377fa61b868af
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043400"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="8bd0c-102">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8bd0c-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="8bd0c-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8bd0c-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8bd0c-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>y se incluye información sobre propiedades.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="8bd0c-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="8bd0c-107">El patrón de control <xref:System.Windows.Automation.GridItemPattern> se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="8bd0c-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8bd0c-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="8bd0c-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="8bd0c-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="8bd0c-110">Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las directrices y convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bd0c-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="8bd0c-111">Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).</span><span class="sxs-lookup"><span data-stu-id="8bd0c-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="8bd0c-112">Las celdas combinadas informarán de sus propiedades <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> según su celda de anclaje subyacente, como define el proveedor de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="8bd0c-113">Normalmente, será la fila o columna superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="8bd0c-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> no permite la manipulación activa de la cuadrícula, como la combinación o la división de celdas.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="8bd0c-115">Los controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> normalmente se pueden atravesar (es decir, un cliente de UI Automation puede moverse a los controles adyacentes) con el teclado.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="8bd0c-116">Miembros requeridos para IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="8bd0c-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="8bd0c-117">Para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="8bd0c-118">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="8bd0c-118">Required members</span></span>|<span data-ttu-id="8bd0c-119">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="8bd0c-119">Member type</span></span>|<span data-ttu-id="8bd0c-120">Notas</span><span class="sxs-lookup"><span data-stu-id="8bd0c-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="8bd0c-121">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd0c-121">Property</span></span>|<span data-ttu-id="8bd0c-122">None</span><span class="sxs-lookup"><span data-stu-id="8bd0c-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="8bd0c-123">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd0c-123">Property</span></span>|<span data-ttu-id="8bd0c-124">None</span><span class="sxs-lookup"><span data-stu-id="8bd0c-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="8bd0c-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd0c-125">Property</span></span>|<span data-ttu-id="8bd0c-126">None</span><span class="sxs-lookup"><span data-stu-id="8bd0c-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="8bd0c-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd0c-127">Property</span></span>|<span data-ttu-id="8bd0c-128">None</span><span class="sxs-lookup"><span data-stu-id="8bd0c-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="8bd0c-129">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8bd0c-129">Property</span></span>|<span data-ttu-id="8bd0c-130">None</span><span class="sxs-lookup"><span data-stu-id="8bd0c-130">None</span></span>|  
  
 <span data-ttu-id="8bd0c-131">Este patrón de control no tiene métodos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="8bd0c-132">Excepciones</span><span class="sxs-lookup"><span data-stu-id="8bd0c-132">Exceptions</span></span>  
 <span data-ttu-id="8bd0c-133">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="8bd0c-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd0c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bd0c-134">See also</span></span>

- [<span data-ttu-id="8bd0c-135">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8bd0c-135">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="8bd0c-136">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8bd0c-136">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="8bd0c-137">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="8bd0c-137">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="8bd0c-138">Implementación del patrón de control Grid de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8bd0c-138">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="8bd0c-139">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8bd0c-139">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="8bd0c-140">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8bd0c-140">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
