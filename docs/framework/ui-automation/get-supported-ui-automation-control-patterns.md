---
title: Obtener patrones de control de UI Automation admitidos
description: Lea un ejemplo en el que se muestra cómo recuperar objetos de patrón de control admitidos de los elementos de automatización de la interfaz de usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 68abe272e91c40932aba5bcf99394c4a8f815c53
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276456"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="19d4b-103">Obtener patrones de control de UI Automation admitidos</span><span class="sxs-lookup"><span data-stu-id="19d4b-103">Get Supported UI Automation Control Patterns</span></span>

> [!NOTE]
> <span data-ttu-id="19d4b-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="19d4b-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="19d4b-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="19d4b-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="19d4b-106">En este tema muestra cómo recuperar los objetos de patrón de control de elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19d4b-106">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="19d4b-107">Obtener todos los patrones de control</span><span class="sxs-lookup"><span data-stu-id="19d4b-107">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="19d4b-108">Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.</span><span class="sxs-lookup"><span data-stu-id="19d4b-108">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="19d4b-109">Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.</span><span class="sxs-lookup"><span data-stu-id="19d4b-109">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="19d4b-110">Se recomienda encarecidamente que un cliente no utilice <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="19d4b-110">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="19d4b-111">El rendimiento puede verse afectado gravemente a medida que este método llama a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente.</span><span class="sxs-lookup"><span data-stu-id="19d4b-111">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="19d4b-112">Si es posible, un cliente debe llamar a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.</span><span class="sxs-lookup"><span data-stu-id="19d4b-112">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="19d4b-113">Obtener un patrón de Control concreto</span><span class="sxs-lookup"><span data-stu-id="19d4b-113">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="19d4b-114">Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.</span><span class="sxs-lookup"><span data-stu-id="19d4b-114">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="19d4b-115">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un patrón concreto.</span><span class="sxs-lookup"><span data-stu-id="19d4b-115">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="19d4b-116">Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera una excepción y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="19d4b-116">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19d4b-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19d4b-117">Example</span></span>  

 <span data-ttu-id="19d4b-118">En el ejemplo siguiente se recupera un valor <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y se obtiene un valor <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="19d4b-118">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="19d4b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="19d4b-119">See also</span></span>

- [<span data-ttu-id="19d4b-120">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="19d4b-120">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
