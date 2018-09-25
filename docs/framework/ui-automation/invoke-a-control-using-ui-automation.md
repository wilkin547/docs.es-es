---
title: Llamar a un control utilizando la UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 7e531e7ecdcc6e5cbdbc770b008d2c07873aca16
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086429"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="6a6ba-102">Llamar a un control utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="6a6ba-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="6a6ba-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6a6ba-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6a6ba-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6a6ba-105">En este tema se muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a6ba-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6a6ba-106">Busque un control que coincida con las condiciones de propiedad específicas recorriendo la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
-   <span data-ttu-id="6a6ba-107">Crear un <xref:System.Windows.Automation.AutomationElement> para cada control.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
-   <span data-ttu-id="6a6ba-108">Obtener un objeto <xref:System.Windows.Automation.InvokePattern> de cualquier elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] encontrado que admita el patrón de control <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
-   <span data-ttu-id="6a6ba-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> para invocar el control desde un controlador de eventos de cliente.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a6ba-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a6ba-110">Example</span></span>  
 <span data-ttu-id="6a6ba-111">En este ejemplo se utiliza el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> de la clase <xref:System.Windows.Automation.AutomationElement> para generar un objeto <xref:System.Windows.Automation.InvokePattern> e invocar un control mediante el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="6a6ba-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a6ba-112">See Also</span></span>  
 [<span data-ttu-id="6a6ba-113">Ejemplo de elemento de menú ExpandCollapsePattern y InvokePattern</span><span class="sxs-lookup"><span data-stu-id="6a6ba-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
