---
title: Implementar el patrón de control TableItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 4374666ba5e03720413614c63b00ba987f81f58f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447085"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="63eb1-102">Implementar el patrón de control TableItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="63eb1-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="63eb1-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="63eb1-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="63eb1-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="63eb1-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="63eb1-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="63eb1-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="63eb1-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="63eb1-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="63eb1-107">El patrón de control <xref:System.Windows.Automation.TableItemPattern> se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="63eb1-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="63eb1-108">El acceso a la funcionalidad de celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="63eb1-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="63eb1-109">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="63eb1-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="63eb1-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="63eb1-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="63eb1-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="63eb1-111">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="63eb1-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="63eb1-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="63eb1-113">Miembros requeridos para ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="63eb1-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="63eb1-114">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="63eb1-114">Required member</span></span>|<span data-ttu-id="63eb1-115">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="63eb1-115">Member type</span></span>|<span data-ttu-id="63eb1-116">Notas</span><span class="sxs-lookup"><span data-stu-id="63eb1-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="63eb1-117">Método</span><span class="sxs-lookup"><span data-stu-id="63eb1-117">Method</span></span>|<span data-ttu-id="63eb1-118">Ninguno</span><span class="sxs-lookup"><span data-stu-id="63eb1-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="63eb1-119">Método</span><span class="sxs-lookup"><span data-stu-id="63eb1-119">Method</span></span>|<span data-ttu-id="63eb1-120">Ninguno</span><span class="sxs-lookup"><span data-stu-id="63eb1-120">None</span></span>|  
  
 <span data-ttu-id="63eb1-121">Este patrón de control no tiene eventos o propiedades asociados.</span><span class="sxs-lookup"><span data-stu-id="63eb1-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="63eb1-122">Excepciones</span><span class="sxs-lookup"><span data-stu-id="63eb1-122">Exceptions</span></span>  
 <span data-ttu-id="63eb1-123">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="63eb1-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63eb1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="63eb1-124">See also</span></span>

- [<span data-ttu-id="63eb1-125">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="63eb1-126">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-126">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="63eb1-127">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="63eb1-127">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="63eb1-128">Implementación del patrón de control Table de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-128">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="63eb1-129">Implementación del patrón de control GridItem de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-129">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="63eb1-130">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-130">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="63eb1-131">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="63eb1-131">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
