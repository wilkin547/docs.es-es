---
title: Navegar entre elementos de UI Automation con TreeWalker
description: Vea un ejemplo de código que muestra cómo desplazarse entre los elementos de automatización de la interfaz de usuario mediante la clase TreeWalker.
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
ms.openlocfilehash: e1784862433083f15d600ea2ec39aee2323bbd12
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168021"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navegar entre elementos de UI Automation con TreeWalker
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene código de ejemplo que muestra cómo desplazarse entre [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] los elementos mediante la <xref:System.Windows.Automation.TreeWalker> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente <xref:System.Windows.Automation.TreeWalker.GetParent%2A> se utiliza para recorrer el [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] árbol hasta que encuentra el elemento raíz o el escritorio. El elemento justo debajo que es la ventana primaria del elemento especificado.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> se usa y <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> para crear un <xref:System.Windows.Forms.TreeView> que muestra un subárbol completo de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementos que están en la vista de control y que están habilitados.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Vea también

- [Obtener elementos de UI Automation](obtaining-ui-automation-elements.md)
