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
ms.openlocfilehash: 3ca609551955b32ad8b63296975ce10f097d9c30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433590"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="48bcb-102">Buscar un elemento de UI Automation basándose en una condición de propiedad</span><span class="sxs-lookup"><span data-stu-id="48bcb-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="48bcb-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="48bcb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="48bcb-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="48bcb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="48bcb-105">Este tema contiene código de ejemplo que muestra cómo buscar un elemento dentro del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] basado en una propiedad o propiedades específicas.</span><span class="sxs-lookup"><span data-stu-id="48bcb-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48bcb-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48bcb-106">Example</span></span>  
 <span data-ttu-id="48bcb-107">En el ejemplo siguiente, se especifica un conjunto de condiciones de propiedad que identifican un determinado elemento (o elementos) de interés en el árbol de <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="48bcb-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="48bcb-108">Después, se realiza una búsqueda de todos los elementos coincidentes con el método <xref:System.Windows.Automation.AutomationElement.FindAll%2A> que incorpora una serie de operaciones booleanas <xref:System.Windows.Automation.AndCondition> para limitar el número de elementos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="48bcb-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48bcb-109">Al buscar desde el <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, debe intentar obtener solo elementos secundarios directos.</span><span class="sxs-lookup"><span data-stu-id="48bcb-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="48bcb-110">Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo que podría producir un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="48bcb-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="48bcb-111">Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="48bcb-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="48bcb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="48bcb-112">See also</span></span>

- <span data-ttu-id="48bcb-113">[Ejemplo de elemento de menú InvokePattern y ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="48bcb-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="48bcb-114">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="48bcb-114">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="48bcb-115">Uso de la propiedad AutomationID</span><span class="sxs-lookup"><span data-stu-id="48bcb-115">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
