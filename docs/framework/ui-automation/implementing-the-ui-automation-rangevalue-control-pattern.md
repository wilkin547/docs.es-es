---
title: Implementar el patrón de control RangeValue de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: 847a8aae3fd0c3d6965c910d19a4cec11cd2a3b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180180"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="817d8-102">Implementar el patrón de control RangeValue de UI Automation</span><span class="sxs-lookup"><span data-stu-id="817d8-102">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="817d8-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="817d8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="817d8-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="817d8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="817d8-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IRangeValueProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="817d8-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="817d8-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="817d8-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="817d8-107">El patrón de control <xref:System.Windows.Automation.RangeValuePattern> se utiliza para admitir controles que se pueden establecer en un valor dentro de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="817d8-107">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="817d8-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="817d8-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="817d8-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="817d8-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="817d8-110">Al implementar el patrón de control Range Value, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="817d8-110">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="817d8-111">Los controles permiten la recalibración de sus propiedades compatibles según las preferencias de usuario o la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="817d8-111">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="817d8-112">Un ejemplo de esto es un control de termómetro que puede establecerse para mostrar la temperatura en grados Fahrenheit o Celsius.</span><span class="sxs-lookup"><span data-stu-id="817d8-112">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="817d8-113">Los controles que tienen valores de intervalo ambiguos, como las barras de progreso o los controles deslizantes, deben tener dichos valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="817d8-113">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="817d8-114">![Barra de progreso.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="817d8-114">![Progress bar.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="817d8-115">Ejemplo de una barra de progreso donde el valor es de tipo entero y los valores de propiedad mínimo y máximo se normalizan en 0 y 100, respectivamente</span><span class="sxs-lookup"><span data-stu-id="817d8-115">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="817d8-116">Miembros requeridos para IRangeValueProvider</span><span class="sxs-lookup"><span data-stu-id="817d8-116">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="817d8-117">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="817d8-117">Required member</span></span>|<span data-ttu-id="817d8-118">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="817d8-118">Member type</span></span>|<span data-ttu-id="817d8-119">Notas</span><span class="sxs-lookup"><span data-stu-id="817d8-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="817d8-120">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-120">Property</span></span>|<span data-ttu-id="817d8-121">None</span><span class="sxs-lookup"><span data-stu-id="817d8-121">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="817d8-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-122">Property</span></span>|<span data-ttu-id="817d8-123">None</span><span class="sxs-lookup"><span data-stu-id="817d8-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="817d8-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-124">Property</span></span>|<span data-ttu-id="817d8-125">None</span><span class="sxs-lookup"><span data-stu-id="817d8-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="817d8-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-126">Property</span></span>|<span data-ttu-id="817d8-127">None</span><span class="sxs-lookup"><span data-stu-id="817d8-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="817d8-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-128">Property</span></span>|<span data-ttu-id="817d8-129">None</span><span class="sxs-lookup"><span data-stu-id="817d8-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="817d8-130">Propiedad</span><span class="sxs-lookup"><span data-stu-id="817d8-130">Property</span></span>|<span data-ttu-id="817d8-131">None</span><span class="sxs-lookup"><span data-stu-id="817d8-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="817d8-132">Métodos</span><span class="sxs-lookup"><span data-stu-id="817d8-132">Methods</span></span>|<span data-ttu-id="817d8-133">None</span><span class="sxs-lookup"><span data-stu-id="817d8-133">None</span></span>|  
  
 <span data-ttu-id="817d8-134">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="817d8-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="817d8-135">Excepciones</span><span class="sxs-lookup"><span data-stu-id="817d8-135">Exceptions</span></span>  
 <span data-ttu-id="817d8-136">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="817d8-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="817d8-137">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="817d8-137">Exception type</span></span>|<span data-ttu-id="817d8-138">Condición</span><span class="sxs-lookup"><span data-stu-id="817d8-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="817d8-139">Se llama a<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> con un valor que es mayor que <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> o menor que <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span><span class="sxs-lookup"><span data-stu-id="817d8-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="817d8-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="817d8-140">See also</span></span>

- [<span data-ttu-id="817d8-141">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="817d8-141">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="817d8-142">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="817d8-142">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="817d8-143">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="817d8-143">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="817d8-144">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="817d8-144">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="817d8-145">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="817d8-145">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
