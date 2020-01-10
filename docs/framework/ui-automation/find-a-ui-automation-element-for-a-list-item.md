---
title: Buscar un elemento de UI Automation para un elemento de lista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741755"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="4db51-102">Buscar un elemento de UI Automation para un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="4db51-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="4db51-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4db51-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4db51-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="4db51-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="4db51-105">En este tema se muestra cómo recuperar un <xref:System.Windows.Automation.AutomationElement> para un elemento de una lista cuando se conoce el índice del elemento.</span><span class="sxs-lookup"><span data-stu-id="4db51-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db51-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db51-106">Example</span></span>  
 <span data-ttu-id="4db51-107">En el ejemplo siguiente se muestran dos maneras de recuperar un elemento especificado de una lista, uno que usa <xref:System.Windows.Automation.TreeWalker> y el otro mediante <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="4db51-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="4db51-108">La primera técnica tiende a ser más rápida para los controles Win32, pero la segunda es más rápida para los controles Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="4db51-108">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="4db51-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4db51-109">See also</span></span>

- [<span data-ttu-id="4db51-110">Obtención de elementos de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4db51-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
