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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 4e8822ce8d33d285475be5ec85d36c5085d46f4b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198246"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="c6926-102">Buscar un elemento de UI Automation para un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="c6926-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="c6926-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c6926-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c6926-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="c6926-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c6926-105">En este tema se muestra cómo recuperar un <xref:System.Windows.Automation.AutomationElement> para un elemento dentro de una lista cuando se conoce el índice del elemento.</span><span class="sxs-lookup"><span data-stu-id="c6926-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6926-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6926-106">Example</span></span>  
 <span data-ttu-id="c6926-107">El ejemplo siguiente muestra dos maneras de recuperar un elemento especificado de una lista, una con <xref:System.Windows.Automation.TreeWalker> y otra usando <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6926-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="c6926-108">La primera técnica tiende a ser más rápido para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles, pero el segundo es más rápido para los controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c6926-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="c6926-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6926-109">See Also</span></span>  
 [<span data-ttu-id="c6926-110">Obtención de elementos de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c6926-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
