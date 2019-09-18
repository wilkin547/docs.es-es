---
title: Navegar entre elementos de UI Automation con TreeWalker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 7ecf6edd37b656f7dd1d7e31506d0dd455592d9b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042981"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="a6c59-102">Navegar entre elementos de UI Automation con TreeWalker</span><span class="sxs-lookup"><span data-stu-id="a6c59-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="a6c59-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a6c59-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a6c59-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a6c59-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a6c59-105">Este tema contiene código de ejemplo que muestra cómo desplazarse entre [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] los elementos mediante la <xref:System.Windows.Automation.TreeWalker> clase.</span><span class="sxs-lookup"><span data-stu-id="a6c59-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c59-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6c59-106">Example</span></span>  
 <span data-ttu-id="a6c59-107">En el ejemplo siguiente <xref:System.Windows.Automation.TreeWalker.GetParent%2A> se utiliza para recorrer [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] el árbol hasta que encuentra el elemento raíz o el escritorio.</span><span class="sxs-lookup"><span data-stu-id="a6c59-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="a6c59-108">El elemento justo debajo que es la ventana primaria del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="a6c59-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="a6c59-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6c59-109">Example</span></span>  
 <span data-ttu-id="a6c59-110">En el ejemplo siguiente <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> se <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> usa y para <xref:System.Windows.Forms.TreeView> crear un que muestra un subárbol [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] completo de elementos que están en la vista de control y que están habilitados.</span><span class="sxs-lookup"><span data-stu-id="a6c59-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="a6c59-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6c59-111">See also</span></span>

- [<span data-ttu-id="a6c59-112">Obtención de elementos de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a6c59-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
