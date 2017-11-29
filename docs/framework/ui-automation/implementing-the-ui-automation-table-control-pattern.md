---
title: "Implementar el patrón de control Table de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4a1fbe175abf07eaccfd177c6e32f5515e88c4ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="4a62d-102">Implementar el patrón de control Table de UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4a62d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4a62d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4a62d-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4a62d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4a62d-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableProvider>, incluida la información sobre propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="4a62d-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="4a62d-106">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="4a62d-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="4a62d-107">El <xref:System.Windows.Automation.TablePattern> patrón de control se usa para admitir controles que actúan como contenedores para una colección de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="4a62d-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="4a62d-108">Los elementos secundarios de este elemento deben implementar <xref:System.Windows.Automation.Provider.ITableItemProvider> y deben estar organizados en un sistema de coordenadas lógico bidimensional que se pueda recorrer por filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="4a62d-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="4a62d-109">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableProvider> también debe exponer una relación de encabezado de columna o fila para cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="4a62d-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="4a62d-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4a62d-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4a62d-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="4a62d-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4a62d-112">Al implementar el patrón de control Table, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="4a62d-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="4a62d-113">Acceso al contenido de celdas individuales es a través de un sistema de coordenadas lógico bidimensional o la matriz proporcionada por la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="4a62d-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
-   <span data-ttu-id="4a62d-114">Un encabezado de columna o fila puede estar dentro de un objeto de tabla o ser un objeto de encabezado independiente asociado a un objeto de tabla.</span><span class="sxs-lookup"><span data-stu-id="4a62d-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
-   <span data-ttu-id="4a62d-115">Los encabezados de fila y columna pueden incluir tanto un encabezado principal como cualquier encabezado auxiliar.</span><span class="sxs-lookup"><span data-stu-id="4a62d-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a62d-116">Este concepto es más evidente en una [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] donde un usuario ha definido una columna "Nombre" de la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4a62d-116">This concept becomes evident in a [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="4a62d-117">Esta columna tiene ahora dos encabezados: el encabezado "Nombre" definido por el usuario y la designación alfanumérica para esa columna asignada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a62d-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
-   <span data-ttu-id="4a62d-118">Vea [implementar el patrón de Control Grid de UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) para la funcionalidad de cuadrícula relacionada.</span><span class="sxs-lookup"><span data-stu-id="4a62d-118">See [Implementing the UI Automation Grid Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="4a62d-119">![Tabla con elementos de encabezado complejos. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="4a62d-119">![Table with complex header items.](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="4a62d-120">Ejemplo de una tabla con encabezados de columna compleja</span><span class="sxs-lookup"><span data-stu-id="4a62d-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="4a62d-121">![Tabla con propiedad RowOrColumnMajor ambigua. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="4a62d-121">![Table with ambiguous RowOrColumnMajor property.](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="4a62d-122">Ejemplo de una tabla con propiedad RowOrColumnMajor ambigua</span><span class="sxs-lookup"><span data-stu-id="4a62d-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="4a62d-123">Miembros requeridos para ITableProvider</span><span class="sxs-lookup"><span data-stu-id="4a62d-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="4a62d-124">Se requieren los siguientes métodos y propiedades para la interfaz de ITableProvider.</span><span class="sxs-lookup"><span data-stu-id="4a62d-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="4a62d-125">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="4a62d-125">Required members</span></span>|<span data-ttu-id="4a62d-126">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="4a62d-126">Member type</span></span>|<span data-ttu-id="4a62d-127">Notas</span><span class="sxs-lookup"><span data-stu-id="4a62d-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="4a62d-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="4a62d-128">Property</span></span>|<span data-ttu-id="4a62d-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4a62d-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="4a62d-130">Método</span><span class="sxs-lookup"><span data-stu-id="4a62d-130">Method</span></span>|<span data-ttu-id="4a62d-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4a62d-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="4a62d-132">Método</span><span class="sxs-lookup"><span data-stu-id="4a62d-132">Method</span></span>|<span data-ttu-id="4a62d-133">Ninguno</span><span class="sxs-lookup"><span data-stu-id="4a62d-133">None</span></span>|  
  
 <span data-ttu-id="4a62d-134">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="4a62d-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4a62d-135">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4a62d-135">Exceptions</span></span>  
 <span data-ttu-id="4a62d-136">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="4a62d-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a62d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a62d-137">See Also</span></span>  
 [<span data-ttu-id="4a62d-138">Información general del patrones de Control UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-138">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4a62d-139">Patrones de Control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-139">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="4a62d-140">Patrones de Control UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="4a62d-140">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="4a62d-141">Implementar el patrón de Control TableItem UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-141">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [<span data-ttu-id="4a62d-142">Implementar el patrón de Control Grid UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-142">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="4a62d-143">Información general sobre el árbol de automatización de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4a62d-143">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="4a62d-144">Usar almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="4a62d-144">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
