---
title: Implementar el patrón de control Toggle de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 5f64842d31d46af3d648b9b570d1cfb210e2910a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180062"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="9ab8b-102">Implementar el patrón de control Toggle de UI Automation</span><span class="sxs-lookup"><span data-stu-id="9ab8b-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="9ab8b-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9ab8b-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="9ab8b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9ab8b-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, incluida la información sobre métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="9ab8b-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="9ab8b-107">El patrón de control <xref:System.Windows.Automation.TogglePattern> se usa para admitir controles que pueden recorrer un conjunto de estados y mantener un estado una vez establecido.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="9ab8b-108">Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9ab8b-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="9ab8b-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="9ab8b-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="9ab8b-110">Al implementar el patrón de control Toggle, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="9ab8b-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="9ab8b-111">Los controles que no mantienen el estado cuando se activan, como botones, botones de barra de herramientas e hipervínculos, deben implementar <xref:System.Windows.Automation.Provider.IInvokeProvider> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="9ab8b-112">Un control debe recorrer su <xref:System.Windows.Automation.ToggleState> en el siguiente orden: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> y, si se admite, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="9ab8b-113"><xref:System.Windows.Automation.TogglePattern> no ofrece un método SetState(newState) debido a problemas relacionados con la configuración directa de una CheckBox de tres estados sin recorrer su secuencia <xref:System.Windows.Automation.ToggleState> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="9ab8b-114">El control RadioButton no implementa <xref:System.Windows.Automation.Provider.IToggleProvider>, ya que no es capaz de recorrer sus estados válidos.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="9ab8b-115">Miembros requeridos para IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="9ab8b-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="9ab8b-116">Para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="9ab8b-117">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="9ab8b-117">Required member</span></span>|<span data-ttu-id="9ab8b-118">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="9ab8b-118">Member type</span></span>|<span data-ttu-id="9ab8b-119">Notas</span><span class="sxs-lookup"><span data-stu-id="9ab8b-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="9ab8b-120">Método</span><span class="sxs-lookup"><span data-stu-id="9ab8b-120">Method</span></span>|<span data-ttu-id="9ab8b-121">None</span><span class="sxs-lookup"><span data-stu-id="9ab8b-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="9ab8b-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="9ab8b-122">Property</span></span>|<span data-ttu-id="9ab8b-123">None</span><span class="sxs-lookup"><span data-stu-id="9ab8b-123">None</span></span>|  
  
 <span data-ttu-id="9ab8b-124">Este patrón de control no tiene eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="9ab8b-125">Excepciones</span><span class="sxs-lookup"><span data-stu-id="9ab8b-125">Exceptions</span></span>  
 <span data-ttu-id="9ab8b-126">Este patrón de control no tiene excepciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="9ab8b-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab8b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ab8b-127">See also</span></span>

- [<span data-ttu-id="9ab8b-128">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="9ab8b-128">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="9ab8b-129">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="9ab8b-129">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="9ab8b-130">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="9ab8b-130">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="9ab8b-131">Obtener el estado de alternancia de una casilla mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="9ab8b-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="9ab8b-132">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="9ab8b-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="9ab8b-133">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="9ab8b-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
