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
ms.openlocfilehash: 63181de26f7d8efda99d5b5d71b006cde44823a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433546"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="79edc-102">Buscar un elemento de UI Automation para un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="79edc-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="79edc-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="79edc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="79edc-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="79edc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="79edc-105">En este tema se muestra cómo recuperar un <xref:System.Windows.Automation.AutomationElement> para un elemento de una lista cuando se conoce el índice del elemento.</span><span class="sxs-lookup"><span data-stu-id="79edc-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79edc-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79edc-106">Example</span></span>  
 <span data-ttu-id="79edc-107">En el ejemplo siguiente se muestran dos maneras de recuperar un elemento especificado de una lista, uno que usa <xref:System.Windows.Automation.TreeWalker> y el otro mediante <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="79edc-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="79edc-108">La primera técnica tiende a ser más rápida para los controles de [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], pero la segunda es más rápida para los controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="79edc-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="79edc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="79edc-109">See also</span></span>

- [<span data-ttu-id="79edc-110">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="79edc-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
