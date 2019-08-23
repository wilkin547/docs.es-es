---
title: Implementar el patrón de control Toggle de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 2293dc77369ecf019bd1093808135eeefd99c115
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932061"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="56899-102">Implementar el patrón de control Toggle de UI Automation</span><span class="sxs-lookup"><span data-stu-id="56899-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="56899-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="56899-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="56899-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="56899-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="56899-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, incluida la información sobre métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="56899-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="56899-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="56899-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="56899-107">El patrón de control <xref:System.Windows.Automation.TogglePattern> se usa para admitir controles que pueden recorrer un conjunto de estados y mantener un estado una vez establecido.</span><span class="sxs-lookup"><span data-stu-id="56899-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="56899-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="56899-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="56899-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="56899-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="56899-110">Al implementar el patrón de control Toggle, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="56899-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="56899-111">Los controles que no mantienen el estado cuando se activan, como botones, botones de barra de herramientas e hipervínculos, deben implementar <xref:System.Windows.Automation.Provider.IInvokeProvider> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="56899-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="56899-112">Un control debe recorrer su <xref:System.Windows.Automation.ToggleState> en el siguiente orden: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> y, si se admite, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="56899-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="56899-113"><xref:System.Windows.Automation.TogglePattern> no ofrece un método SetState(newState) debido a problemas relacionados con la configuración directa de una CheckBox de tres estados sin recorrer su secuencia <xref:System.Windows.Automation.ToggleState> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="56899-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="56899-114">El control RadioButton no implementa <xref:System.Windows.Automation.Provider.IToggleProvider>, ya que no es capaz de recorrer sus estados válidos.</span><span class="sxs-lookup"><span data-stu-id="56899-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="56899-115">Miembros requeridos para IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="56899-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="56899-116">Para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="56899-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="56899-117">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="56899-117">Required member</span></span>|<span data-ttu-id="56899-118">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="56899-118">Member type</span></span>|<span data-ttu-id="56899-119">Notas</span><span class="sxs-lookup"><span data-stu-id="56899-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="56899-120">Método</span><span class="sxs-lookup"><span data-stu-id="56899-120">Method</span></span>|<span data-ttu-id="56899-121">None</span><span class="sxs-lookup"><span data-stu-id="56899-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="56899-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="56899-122">Property</span></span>|<span data-ttu-id="56899-123">None</span><span class="sxs-lookup"><span data-stu-id="56899-123">None</span></span>|  
  
 <span data-ttu-id="56899-124">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="56899-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="56899-125">Excepciones</span><span class="sxs-lookup"><span data-stu-id="56899-125">Exceptions</span></span>  
 <span data-ttu-id="56899-126">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="56899-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56899-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="56899-127">See also</span></span>

- [<span data-ttu-id="56899-128">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="56899-128">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="56899-129">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="56899-129">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="56899-130">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="56899-130">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="56899-131">Obtención del estado de alternancia de una casilla mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="56899-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="56899-132">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="56899-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="56899-133">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="56899-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
