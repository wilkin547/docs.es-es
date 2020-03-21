---
title: Implementar el patrón de control TableItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: f35b491c31e8725eac0025dfd6815079d0ea9b79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180077"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="fb416-102">Implementar el patrón de control TableItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fb416-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="fb416-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fb416-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fb416-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="fb416-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="fb416-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="fb416-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="fb416-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="fb416-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="fb416-107">El patrón de control <xref:System.Windows.Automation.TableItemPattern> se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="fb416-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="fb416-108">El acceso a la funcionalidad de celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="fb416-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="fb416-109">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="fb416-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="fb416-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fb416-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="fb416-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="fb416-111">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="fb416-112">Para obtener información sobre la funcionalidad de elementos de cuadrícula relacionados, vea [Implementación del patrón](implementing-the-ui-automation-griditem-control-pattern.md)de control GridItem de Automatización de la interfaz de usuarioUI Automation .</span><span class="sxs-lookup"><span data-stu-id="fb416-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="fb416-113">Miembros requeridos para ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="fb416-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="fb416-114">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="fb416-114">Required member</span></span>|<span data-ttu-id="fb416-115">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="fb416-115">Member type</span></span>|<span data-ttu-id="fb416-116">Notas</span><span class="sxs-lookup"><span data-stu-id="fb416-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="fb416-117">Método</span><span class="sxs-lookup"><span data-stu-id="fb416-117">Method</span></span>|<span data-ttu-id="fb416-118">None</span><span class="sxs-lookup"><span data-stu-id="fb416-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="fb416-119">Método</span><span class="sxs-lookup"><span data-stu-id="fb416-119">Method</span></span>|<span data-ttu-id="fb416-120">None</span><span class="sxs-lookup"><span data-stu-id="fb416-120">None</span></span>|  
  
 <span data-ttu-id="fb416-121">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="fb416-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="fb416-122">Excepciones</span><span class="sxs-lookup"><span data-stu-id="fb416-122">Exceptions</span></span>  
 <span data-ttu-id="fb416-123">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="fb416-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb416-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb416-124">See also</span></span>

- [<span data-ttu-id="fb416-125">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="fb416-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="fb416-126">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fb416-126">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="fb416-127">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="fb416-127">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="fb416-128">Implementar el patrón de control Table de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fb416-128">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="fb416-129">Implementar el patrón de control GridItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fb416-129">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="fb416-130">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="fb416-130">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="fb416-131">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="fb416-131">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
