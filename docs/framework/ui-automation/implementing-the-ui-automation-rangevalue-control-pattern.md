---
title: Implementar el patrón de control RangeValue de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: aeb14bddf98adf53a52c8897994bd0fb6fa498ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61983473"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="bfc44-102">Implementar el patrón de control RangeValue de UI Automation</span><span class="sxs-lookup"><span data-stu-id="bfc44-102">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="bfc44-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="bfc44-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bfc44-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="bfc44-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="bfc44-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IRangeValueProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="bfc44-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="bfc44-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="bfc44-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="bfc44-107">El patrón de control <xref:System.Windows.Automation.RangeValuePattern> se utiliza para admitir controles que se pueden establecer en un valor dentro de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="bfc44-107">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="bfc44-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bfc44-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="bfc44-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="bfc44-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="bfc44-110">Al implementar el patrón de control Range Value, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="bfc44-110">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="bfc44-111">Los controles permiten la recalibración de sus propiedades compatibles según las preferencias de usuario o la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="bfc44-111">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="bfc44-112">Un ejemplo de esto es un control de termómetro que puede establecerse para mostrar la temperatura en grados Fahrenheit o Celsius.</span><span class="sxs-lookup"><span data-stu-id="bfc44-112">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="bfc44-113">Los controles que tienen valores de intervalo ambiguos, como las barras de progreso o los controles deslizantes, deben tener dichos valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="bfc44-113">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="bfc44-114">![Barra de progreso. ](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="bfc44-114">![Progress bar.](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="bfc44-115">Ejemplo de una barra de progreso donde el valor es de tipo entero y los valores de propiedad mínimo y máximo se normalizan en 0 y 100, respectivamente</span><span class="sxs-lookup"><span data-stu-id="bfc44-115">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>   
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="bfc44-116">Miembros requeridos para IRangeValueProvider</span><span class="sxs-lookup"><span data-stu-id="bfc44-116">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="bfc44-117">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="bfc44-117">Required member</span></span>|<span data-ttu-id="bfc44-118">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="bfc44-118">Member type</span></span>|<span data-ttu-id="bfc44-119">Notas</span><span class="sxs-lookup"><span data-stu-id="bfc44-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="bfc44-120">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-120">Property</span></span>|<span data-ttu-id="bfc44-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-121">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="bfc44-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-122">Property</span></span>|<span data-ttu-id="bfc44-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="bfc44-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-124">Property</span></span>|<span data-ttu-id="bfc44-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="bfc44-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-126">Property</span></span>|<span data-ttu-id="bfc44-127">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="bfc44-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-128">Property</span></span>|<span data-ttu-id="bfc44-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="bfc44-130">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bfc44-130">Property</span></span>|<span data-ttu-id="bfc44-131">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="bfc44-132">Métodos</span><span class="sxs-lookup"><span data-stu-id="bfc44-132">Methods</span></span>|<span data-ttu-id="bfc44-133">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfc44-133">None</span></span>|  
  
 <span data-ttu-id="bfc44-134">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="bfc44-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="bfc44-135">Excepciones</span><span class="sxs-lookup"><span data-stu-id="bfc44-135">Exceptions</span></span>  
 <span data-ttu-id="bfc44-136">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="bfc44-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="bfc44-137">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="bfc44-137">Exception type</span></span>|<span data-ttu-id="bfc44-138">Condición</span><span class="sxs-lookup"><span data-stu-id="bfc44-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="bfc44-139">Se llama a<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> con un valor que es mayor que <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> o menor que <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span><span class="sxs-lookup"><span data-stu-id="bfc44-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfc44-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfc44-140">See also</span></span>

- [<span data-ttu-id="bfc44-141">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bfc44-141">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="bfc44-142">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bfc44-142">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="bfc44-143">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="bfc44-143">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="bfc44-144">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bfc44-144">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="bfc44-145">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bfc44-145">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
