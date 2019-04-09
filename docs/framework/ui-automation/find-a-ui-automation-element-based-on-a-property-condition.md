---
title: Buscar un elemento de UI Automation basándose en una condición de propiedad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: a5e775c69a4dd520d8148bfc790cc00428d9d15e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175518"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="32ccf-102">Buscar un elemento de UI Automation basándose en una condición de propiedad</span><span class="sxs-lookup"><span data-stu-id="32ccf-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
>  <span data-ttu-id="32ccf-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="32ccf-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="32ccf-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="32ccf-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="32ccf-105">En este tema contiene código de ejemplo que muestra cómo buscar un elemento dentro de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] en forma de árbol en una o varias propiedades específicas.</span><span class="sxs-lookup"><span data-stu-id="32ccf-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32ccf-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32ccf-106">Example</span></span>  
 <span data-ttu-id="32ccf-107">En el ejemplo siguiente, un conjunto de condiciones de propiedades se especifican que identifican un elemento determinado (o elementos) de interés en el <xref:System.Windows.Automation.AutomationElement> árbol.</span><span class="sxs-lookup"><span data-stu-id="32ccf-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="32ccf-108">A continuación, se realiza una búsqueda para todos los elementos coincidentes con el <xref:System.Windows.Automation.AutomationElement.FindAll%2A> método que incorpora una serie de <xref:System.Windows.Automation.AndCondition> operaciones booleanas para limitar el número de elementos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="32ccf-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32ccf-109">Al realizar búsquedas desde el <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, debería intentar obtener solo los elementos secundarios directos.</span><span class="sxs-lookup"><span data-stu-id="32ccf-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="32ccf-110">Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo cual un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="32ccf-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="32ccf-111">Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="32ccf-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="32ccf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="32ccf-112">See also</span></span>

- [<span data-ttu-id="32ccf-113">Ejemplo de elemento de menú ExpandCollapsePattern y InvokePattern</span><span class="sxs-lookup"><span data-stu-id="32ccf-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [<span data-ttu-id="32ccf-114">Obtener elementos de UI Automation</span><span class="sxs-lookup"><span data-stu-id="32ccf-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [<span data-ttu-id="32ccf-115">Utilizar la propiedad AutomationID</span><span class="sxs-lookup"><span data-stu-id="32ccf-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
