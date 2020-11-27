---
title: Implementación del patrón de control Transform de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control Transform en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz ITransformProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: fc47170a08ff08f6cd8f67996ef8fbf19c40f819
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265653"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="b072d-104">Implementación del patrón de control Transform de UI Automation</span><span class="sxs-lookup"><span data-stu-id="b072d-104">Implementing the UI Automation Transform Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="b072d-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b072d-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b072d-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="b072d-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b072d-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITransformProvider>, incluida la información sobre propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="b072d-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="b072d-108">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="b072d-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="b072d-109">El patrón de control <xref:System.Windows.Automation.TransformPattern> se utsa para admitir controles que se pueden mover, cambiar de tamaño o girar dentro de un espacio bidimensional.</span><span class="sxs-lookup"><span data-stu-id="b072d-109">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="b072d-110">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b072d-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="b072d-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="b072d-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="b072d-112">Al implementar el patrón de control Transform, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="b072d-112">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="b072d-113">La compatibilidad con este patrón de control no se limita a los objetos del escritorio.</span><span class="sxs-lookup"><span data-stu-id="b072d-113">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="b072d-114">Este patrón de control también lo admite los elementos secundarios de un objeto contenedor si los elementos secundarios se pueden mover, cambiar de tamaño o girar libremente dentro de los límites del contenedor.</span><span class="sxs-lookup"><span data-stu-id="b072d-114">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="b072d-115">Un objeto no se puede mover, cambiar de tamaño o girar de manera que su ubicación en pantalla resultante quede completamente fuera de las coordenadas de su contenedor y que, por tanto, sea inaccesible para el teclado o el mouse (por ejemplo, cuando una ventana de nivel superior se mueva fuera de la pantalla o un objeto secundario se mueva fuera de los límites de la ventanilla del contenedor).</span><span class="sxs-lookup"><span data-stu-id="b072d-115">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="b072d-116">En estos casos, el objeto se coloca lo más cerca posible de las coordenadas de pantalla solicitadas reemplazando las coordenadas superiores o izquierdas para que se encuentren dentro de los límites del contenedor.</span><span class="sxs-lookup"><span data-stu-id="b072d-116">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="b072d-117">Para sistemas de varios monitores, si se mueve un objeto, cambia de tamaño o gira completamente fuera de las coordenadas de pantalla de escritorio combinadas, el objeto se coloca en el monitor principal lo más cerca posible de las coordenadas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="b072d-117">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="b072d-118">Todos los parámetros y los valores de propiedad son absolutos e independientes de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="b072d-118">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="b072d-119">Miembros requeridos para ITransformProvider</span><span class="sxs-lookup"><span data-stu-id="b072d-119">Required Members for ITransformProvider</span></span>  

 <span data-ttu-id="b072d-120">Para implementar <xref:System.Windows.Automation.Provider.ITransformProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="b072d-120">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="b072d-121">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="b072d-121">Required members</span></span>|<span data-ttu-id="b072d-122">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="b072d-122">Member type</span></span>|<span data-ttu-id="b072d-123">Notas</span><span class="sxs-lookup"><span data-stu-id="b072d-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="b072d-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b072d-124">Property</span></span>|<span data-ttu-id="b072d-125">None</span><span class="sxs-lookup"><span data-stu-id="b072d-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="b072d-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b072d-126">Property</span></span>|<span data-ttu-id="b072d-127">None</span><span class="sxs-lookup"><span data-stu-id="b072d-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="b072d-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b072d-128">Property</span></span>|<span data-ttu-id="b072d-129">None</span><span class="sxs-lookup"><span data-stu-id="b072d-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="b072d-130">Método</span><span class="sxs-lookup"><span data-stu-id="b072d-130">Method</span></span>|<span data-ttu-id="b072d-131">None</span><span class="sxs-lookup"><span data-stu-id="b072d-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="b072d-132">Método</span><span class="sxs-lookup"><span data-stu-id="b072d-132">Method</span></span>|<span data-ttu-id="b072d-133">None</span><span class="sxs-lookup"><span data-stu-id="b072d-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="b072d-134">Método</span><span class="sxs-lookup"><span data-stu-id="b072d-134">Method</span></span>|<span data-ttu-id="b072d-135">None</span><span class="sxs-lookup"><span data-stu-id="b072d-135">None</span></span>|  
  
 <span data-ttu-id="b072d-136">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="b072d-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="b072d-137">Excepciones</span><span class="sxs-lookup"><span data-stu-id="b072d-137">Exceptions</span></span>  

 <span data-ttu-id="b072d-138">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="b072d-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="b072d-139">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="b072d-139">Exception Type</span></span>|<span data-ttu-id="b072d-140">Condición</span><span class="sxs-lookup"><span data-stu-id="b072d-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="b072d-141">-Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> es false.</span><span class="sxs-lookup"><span data-stu-id="b072d-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="b072d-142">-Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> es false.</span><span class="sxs-lookup"><span data-stu-id="b072d-142">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="b072d-143">-Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> es false.</span><span class="sxs-lookup"><span data-stu-id="b072d-143">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b072d-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="b072d-144">See also</span></span>

- [<span data-ttu-id="b072d-145">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="b072d-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="b072d-146">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="b072d-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="b072d-147">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="b072d-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="b072d-148">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="b072d-148">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="b072d-149">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="b072d-149">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
