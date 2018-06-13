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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 84774cbc3ca3741e7c46397249dcec617d26e8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407511"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navegar entre elementos de UI Automation con TreeWalker
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo navegar entre [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementos mediante el uso de la <xref:System.Windows.Automation.TreeWalker> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Automation.TreeWalker.GetParent%2A> para recorrer el [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] árbol hasta que encuentra el elemento raíz o el escritorio. El elemento inmediatamente inferior es la ventana primaria del elemento especificado.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> y <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> para crear un <xref:System.Windows.Forms.TreeView> que muestra un subárbol completo de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementos que están en la vista de control y que están habilitadas.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Vea también  
 [Obtención de elementos de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
