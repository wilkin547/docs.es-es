---
title: Implementar el patrón de control Table de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control Table en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz ITableProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 9c1d57e46aed9ec2441a95544d26244d2dfa9496
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265757"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="fd172-104">Implementar el patrón de control Table de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-104">Implementing the UI Automation Table Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="fd172-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fd172-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fd172-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="fd172-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="fd172-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableProvider>, incluida la información sobre propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="fd172-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="fd172-108">Al final de la información general se proporcionan vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="fd172-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="fd172-109">El patrón de control <xref:System.Windows.Automation.TablePattern> se usa para admitir controles que actúen como contenedores para una colección de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fd172-109">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="fd172-110">Los elementos secundarios de este elemento deben implementar <xref:System.Windows.Automation.Provider.ITableItemProvider> y organizarse en un sistema de coordenadas lógico bidimensional que se pueda recorrer por filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="fd172-110">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="fd172-111">Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableProvider> también debe exponer una relación de encabezado de columna o fila para cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="fd172-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="fd172-112">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fd172-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="fd172-113">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="fd172-113">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="fd172-114">Al implementar el patrón de control Table, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="fd172-114">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="fd172-115">El acceso al contenido de celdas individuales se realiza a través de un sistema de coordenadas lógico bidimensional o la matriz ofrecida por la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="fd172-115">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="fd172-116">Un encabezado de columna o fila puede estar dentro de un objeto de tabla o ser un objeto de encabezado independiente asociado a un objeto de tabla.</span><span class="sxs-lookup"><span data-stu-id="fd172-116">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="fd172-117">Los encabezados de fila y columna pueden incluir tanto un encabezado principal como cualquier encabezado auxiliar.</span><span class="sxs-lookup"><span data-stu-id="fd172-117">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd172-118">Este concepto se vuelve evidente en una hoja de cálculo de Microsoft Excel en la que un usuario ha definido una columna "nombre".</span><span class="sxs-lookup"><span data-stu-id="fd172-118">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="fd172-119">Esta columna tiene ahora dos encabezados: el encabezado "Nombre" definido por el usuario y la designación alfanumérica para esa columna asignada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd172-119">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="fd172-120">Vea [implementar el patrón de control Grid de UI Automation](implementing-the-ui-automation-grid-control-pattern.md) para la funcionalidad de cuadrícula relacionada.</span><span class="sxs-lookup"><span data-stu-id="fd172-120">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="fd172-121">![Tabla con elementos de encabezado complejos.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="fd172-121">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="fd172-122">Ejemplo de una tabla con encabezados de columna compleja</span><span class="sxs-lookup"><span data-stu-id="fd172-122">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="fd172-123">![Tabla con propiedad RowOrColumnMajor ambigua.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="fd172-123">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="fd172-124">Ejemplo de una tabla con propiedad RowOrColumnMajor ambigua</span><span class="sxs-lookup"><span data-stu-id="fd172-124">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>

## <a name="required-members-for-itableprovider"></a><span data-ttu-id="fd172-125">Miembros requeridos para ITableProvider</span><span class="sxs-lookup"><span data-stu-id="fd172-125">Required Members for ITableProvider</span></span>  

 <span data-ttu-id="fd172-126">Se requieren los siguientes métodos y propiedades para la interfaz de ITableProvider.</span><span class="sxs-lookup"><span data-stu-id="fd172-126">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="fd172-127">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="fd172-127">Required members</span></span>|<span data-ttu-id="fd172-128">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="fd172-128">Member type</span></span>|<span data-ttu-id="fd172-129">Notas</span><span class="sxs-lookup"><span data-stu-id="fd172-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="fd172-130">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fd172-130">Property</span></span>|<span data-ttu-id="fd172-131">None</span><span class="sxs-lookup"><span data-stu-id="fd172-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="fd172-132">Método</span><span class="sxs-lookup"><span data-stu-id="fd172-132">Method</span></span>|<span data-ttu-id="fd172-133">None</span><span class="sxs-lookup"><span data-stu-id="fd172-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="fd172-134">Método</span><span class="sxs-lookup"><span data-stu-id="fd172-134">Method</span></span>|<span data-ttu-id="fd172-135">None</span><span class="sxs-lookup"><span data-stu-id="fd172-135">None</span></span>|  
  
 <span data-ttu-id="fd172-136">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="fd172-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="fd172-137">Excepciones</span><span class="sxs-lookup"><span data-stu-id="fd172-137">Exceptions</span></span>  

 <span data-ttu-id="fd172-138">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="fd172-138">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd172-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd172-139">See also</span></span>

- [<span data-ttu-id="fd172-140">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-140">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="fd172-141">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-141">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="fd172-142">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="fd172-142">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="fd172-143">Implementar el patrón de control TableItem de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-143">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="fd172-144">Implementar el patrón de control Grid de UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-144">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="fd172-145">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-145">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="fd172-146">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="fd172-146">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
