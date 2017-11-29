---
title: "Implementar el patrón de control TableItem de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5861ab24627f9b78cd20f97fcdb1b1b3d681991a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="42a6f-102">Implementar el patrón de control TableItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="42a6f-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="42a6f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="42a6f-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="42a6f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="42a6f-105">En este tema se presenta las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="42a6f-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="42a6f-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="42a6f-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="42a6f-107">El <xref:System.Windows.Automation.TableItemPattern> patrón de control se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="42a6f-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="42a6f-108">Acceso a la funcionalidad de la celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="42a6f-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="42a6f-109">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider> con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="42a6f-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="42a6f-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="42a6f-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="42a6f-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="42a6f-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="42a6f-112">Para la funcionalidad del elemento de cuadrícula relacionada, consulte [implementar el patrón de Control GridItem de UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="42a6f-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="42a6f-113">Miembros requeridos para ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="42a6f-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="42a6f-114">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="42a6f-114">Required member</span></span>|<span data-ttu-id="42a6f-115">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="42a6f-115">Member type</span></span>|<span data-ttu-id="42a6f-116">Notas</span><span class="sxs-lookup"><span data-stu-id="42a6f-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="42a6f-117">Método</span><span class="sxs-lookup"><span data-stu-id="42a6f-117">Method</span></span>|<span data-ttu-id="42a6f-118">Ninguno</span><span class="sxs-lookup"><span data-stu-id="42a6f-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="42a6f-119">Método</span><span class="sxs-lookup"><span data-stu-id="42a6f-119">Method</span></span>|<span data-ttu-id="42a6f-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="42a6f-120">None</span></span>|  
  
 <span data-ttu-id="42a6f-121">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="42a6f-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="42a6f-122">Excepciones</span><span class="sxs-lookup"><span data-stu-id="42a6f-122">Exceptions</span></span>  
 <span data-ttu-id="42a6f-123">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="42a6f-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a6f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a6f-124">See Also</span></span>  
 [<span data-ttu-id="42a6f-125">Información general del patrones de Control UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="42a6f-126">Patrones de Control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="42a6f-127">Patrones de Control UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="42a6f-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="42a6f-128">Implementar el patrón de Control Table UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="42a6f-129">Implementar el patrón de Control GridItem UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="42a6f-130">Información general sobre el árbol de automatización de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="42a6f-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="42a6f-131">Usar almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="42a6f-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
