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
manager: markl
ms.openlocfilehash: 89e528e7ff3dbeeba30307adf83434b83f540221
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408329"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="5e304-102">Llamar a un control utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="5e304-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="5e304-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5e304-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5e304-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5e304-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5e304-105">En este tema se muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e304-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5e304-106">Busque un control que coincida con las condiciones de propiedad específicas recorriendo la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="5e304-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
-   <span data-ttu-id="5e304-107">Crear un <xref:System.Windows.Automation.AutomationElement> para cada control.</span><span class="sxs-lookup"><span data-stu-id="5e304-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
-   <span data-ttu-id="5e304-108">Obtener un objeto <xref:System.Windows.Automation.InvokePattern> de cualquier elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] encontrado que admita el patrón de control <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="5e304-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
-   <span data-ttu-id="5e304-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> para invocar el control desde un controlador de eventos de cliente.</span><span class="sxs-lookup"><span data-stu-id="5e304-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e304-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e304-110">Example</span></span>  
 <span data-ttu-id="5e304-111">En este ejemplo se utiliza el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> de la clase <xref:System.Windows.Automation.AutomationElement> para generar un objeto <xref:System.Windows.Automation.InvokePattern> e invocar un control mediante el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="5e304-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="5e304-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e304-112">See Also</span></span>  
 [<span data-ttu-id="5e304-113">Ejemplo de elemento de menú ExpandCollapsePattern y InvokePattern</span><span class="sxs-lookup"><span data-stu-id="5e304-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
