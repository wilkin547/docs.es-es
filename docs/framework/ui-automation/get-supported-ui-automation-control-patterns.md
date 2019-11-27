---
title: Obtener patrones de control de UI Automation admitidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: b1da13cf5eb39a61f40848a5f199cfd39b16d7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435639"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="7f40e-102">Obtener patrones de control de UI Automation admitidos</span><span class="sxs-lookup"><span data-stu-id="7f40e-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
> <span data-ttu-id="7f40e-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="7f40e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7f40e-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="7f40e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="7f40e-105">En este tema muestra cómo recuperar los objetos de patrón de control de elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f40e-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="7f40e-106">Obtener todos los patrones de control</span><span class="sxs-lookup"><span data-stu-id="7f40e-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="7f40e-107">Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.</span><span class="sxs-lookup"><span data-stu-id="7f40e-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="7f40e-108">Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.</span><span class="sxs-lookup"><span data-stu-id="7f40e-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7f40e-109">Se recomienda encarecidamente que un cliente no utilice <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f40e-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="7f40e-110">El rendimiento puede verse afectado gravemente a medida que este método llama a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente.</span><span class="sxs-lookup"><span data-stu-id="7f40e-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="7f40e-111">Si es posible, un cliente debe llamar a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.</span><span class="sxs-lookup"><span data-stu-id="7f40e-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="7f40e-112">Obtener un patrón de Control concreto</span><span class="sxs-lookup"><span data-stu-id="7f40e-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="7f40e-113">Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.</span><span class="sxs-lookup"><span data-stu-id="7f40e-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="7f40e-114">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un patrón concreto.</span><span class="sxs-lookup"><span data-stu-id="7f40e-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="7f40e-115">Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera una excepción y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="7f40e-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f40e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f40e-116">Example</span></span>  
 <span data-ttu-id="7f40e-117">En el ejemplo siguiente se recupera un valor <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y se obtiene un valor <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="7f40e-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="7f40e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f40e-118">See also</span></span>

- [<span data-ttu-id="7f40e-119">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="7f40e-119">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
