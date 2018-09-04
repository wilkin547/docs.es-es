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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b0bc694148dbd91cd9e942a3f051aea9362fc150
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511481"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="b8e20-102">Obtener patrones de control de UI Automation admitidos</span><span class="sxs-lookup"><span data-stu-id="b8e20-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="b8e20-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b8e20-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b8e20-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="b8e20-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b8e20-105">En este tema se muestra cómo recuperar los objetos de patrón de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementos.</span><span class="sxs-lookup"><span data-stu-id="b8e20-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="b8e20-106">Obtener todos los patrones de control</span><span class="sxs-lookup"><span data-stu-id="b8e20-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="b8e20-107">Obtener el <xref:System.Windows.Automation.AutomationElement> cuyo control patrones está interesado.</span><span class="sxs-lookup"><span data-stu-id="b8e20-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="b8e20-108">Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.</span><span class="sxs-lookup"><span data-stu-id="b8e20-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b8e20-109">Se recomienda encarecidamente que no use un cliente <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8e20-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="b8e20-110">Rendimiento puede verse afectado gravemente a medida que este método llama <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente.</span><span class="sxs-lookup"><span data-stu-id="b8e20-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="b8e20-111">Si es posible, debe llamar un cliente <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.</span><span class="sxs-lookup"><span data-stu-id="b8e20-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="b8e20-112">Obtener un patrón de Control concreto</span><span class="sxs-lookup"><span data-stu-id="b8e20-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="b8e20-113">Obtener el <xref:System.Windows.Automation.AutomationElement> cuyo control patrones está interesado.</span><span class="sxs-lookup"><span data-stu-id="b8e20-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="b8e20-114">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un modelo concreto.</span><span class="sxs-lookup"><span data-stu-id="b8e20-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="b8e20-115">Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> produce una excepción, y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="b8e20-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8e20-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e20-116">Example</span></span>  
 <span data-ttu-id="b8e20-117">En el ejemplo siguiente se recupera un <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y obtiene un <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="b8e20-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="b8e20-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e20-118">See Also</span></span>  
 [<span data-ttu-id="b8e20-119">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="b8e20-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
