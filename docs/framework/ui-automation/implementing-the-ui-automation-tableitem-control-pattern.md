---
title: Implementar el patrón de control TableItem de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control TableItem en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz ITableItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 5e83f68772de3026fe8bcb265a11999e0b85a164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265679"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="f8d20-104">Implementar el patrón de control TableItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-104">Implementing the UI Automation TableItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="f8d20-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f8d20-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f8d20-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="f8d20-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="f8d20-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="f8d20-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="f8d20-108">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="f8d20-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="f8d20-109">El patrón de control <xref:System.Windows.Automation.TableItemPattern> se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="f8d20-109">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="f8d20-110">El acceso a la funcionalidad de celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="f8d20-110">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="f8d20-111">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="f8d20-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="f8d20-112">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f8d20-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f8d20-113">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="f8d20-113">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="f8d20-114">Para obtener la funcionalidad de elemento de cuadrícula relacionada, vea [implementar el patrón de control GridItem de UI Automation](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f8d20-114">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>

## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="f8d20-115">Miembros requeridos para ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="f8d20-115">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="f8d20-116">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="f8d20-116">Required member</span></span>|<span data-ttu-id="f8d20-117">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="f8d20-117">Member type</span></span>|<span data-ttu-id="f8d20-118">Notas</span><span class="sxs-lookup"><span data-stu-id="f8d20-118">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="f8d20-119">Método</span><span class="sxs-lookup"><span data-stu-id="f8d20-119">Method</span></span>|<span data-ttu-id="f8d20-120">None</span><span class="sxs-lookup"><span data-stu-id="f8d20-120">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="f8d20-121">Método</span><span class="sxs-lookup"><span data-stu-id="f8d20-121">Method</span></span>|<span data-ttu-id="f8d20-122">None</span><span class="sxs-lookup"><span data-stu-id="f8d20-122">None</span></span>|  
  
 <span data-ttu-id="f8d20-123">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="f8d20-123">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="f8d20-124">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f8d20-124">Exceptions</span></span>  

 <span data-ttu-id="f8d20-125">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="f8d20-125">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d20-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8d20-126">See also</span></span>

- [<span data-ttu-id="f8d20-127">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-127">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="f8d20-128">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-128">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="f8d20-129">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="f8d20-129">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="f8d20-130">Implementar el patrón de control Table de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-130">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="f8d20-131">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-131">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="f8d20-132">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="f8d20-133">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="f8d20-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
