---
title: Llamar a un control utilizando la UI Automation
description: Utilice la automatización de la interfaz de usuario para buscar un control que coincida con ciertas condiciones de propiedad, crear un AutomationElement, obtener un InvokePattern y usar Invoke en el control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 2347a620aab848bf6bcc649a9780aa5a3a520822
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168178"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="52a53-103">Llamar a un control utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="52a53-103">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="52a53-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="52a53-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="52a53-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="52a53-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="52a53-106">En este tema se muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="52a53-106">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="52a53-107">Busque un control que coincida con las condiciones de propiedad específicas recorriendo la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="52a53-107">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="52a53-108">Crear un <xref:System.Windows.Automation.AutomationElement> para cada control.</span><span class="sxs-lookup"><span data-stu-id="52a53-108">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="52a53-109">Obtener un objeto <xref:System.Windows.Automation.InvokePattern> de cualquier elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] encontrado que admita el patrón de control <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="52a53-109">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="52a53-110">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> para invocar el control desde un controlador de eventos de cliente.</span><span class="sxs-lookup"><span data-stu-id="52a53-110">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52a53-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52a53-111">Example</span></span>  
 <span data-ttu-id="52a53-112">En este ejemplo se utiliza el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> de la clase <xref:System.Windows.Automation.AutomationElement> para generar un objeto <xref:System.Windows.Automation.InvokePattern> e invocar un control mediante el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="52a53-112">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="52a53-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="52a53-113">See also</span></span>

- [<span data-ttu-id="52a53-114">Ejemplo de InvokePattern, ExpandCollapsePattern y TogglePattern</span><span class="sxs-lookup"><span data-stu-id="52a53-114">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
