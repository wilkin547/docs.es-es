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
ms.openlocfilehash: 536a71532f02782f9e84bb2bd086af212a77c0da
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043665"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="b04d4-102">Buscar un elemento de UI Automation basándose en una condición de propiedad</span><span class="sxs-lookup"><span data-stu-id="b04d4-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="b04d4-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b04d4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b04d4-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b04d4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b04d4-105">Este tema contiene código de ejemplo que muestra cómo buscar un elemento dentro del [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol basándose en una propiedad o propiedades específicas.</span><span class="sxs-lookup"><span data-stu-id="b04d4-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b04d4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b04d4-106">Example</span></span>  
 <span data-ttu-id="b04d4-107">En el ejemplo siguiente, se especifica un conjunto de condiciones de propiedad que identifican un determinado elemento (o elementos) de interés <xref:System.Windows.Automation.AutomationElement> en el árbol.</span><span class="sxs-lookup"><span data-stu-id="b04d4-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="b04d4-108">Después, se realiza una búsqueda de todos los elementos coincidentes con el <xref:System.Windows.Automation.AutomationElement.FindAll%2A> método que incorpora una serie de <xref:System.Windows.Automation.AndCondition> operaciones booleanas para limitar el número de elementos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="b04d4-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b04d4-109">Al buscar desde el <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, debe intentar obtener solo elementos secundarios directos.</span><span class="sxs-lookup"><span data-stu-id="b04d4-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="b04d4-110">Una búsqueda de descendientes puede iterar a través de cientos o incluso miles de elementos, lo que podría producir un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="b04d4-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="b04d4-111">Si intenta obtener un elemento concreto en un nivel inferior, debe iniciar la búsqueda desde la ventana de aplicación o desde un contenedor en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="b04d4-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="b04d4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b04d4-112">See also</span></span>

- <span data-ttu-id="b04d4-113">[Ejemplo de elemento de menú InvokePattern y ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b04d4-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="b04d4-114">Obtención de elementos de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b04d4-114">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="b04d4-115">Uso de la propiedad AutomationID</span><span class="sxs-lookup"><span data-stu-id="b04d4-115">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
