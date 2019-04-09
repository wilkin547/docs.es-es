---
title: Filtrar para asociar un menú contextual a un nodo TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: ba29e86f62c8d56b0d300d1841a70f434087dd84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100027"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Filtrar para asociar un menú contextual a un nodo TreeView
Los formularios de Windows <xref:System.Windows.Forms.TreeView> control muestra una jerarquía de nodos, similares a los archivos y carpetas que se muestra en el panel izquierdo del explorador de Windows. Estableciendo el <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando haga clic en el <xref:System.Windows.Forms.TreeView> control. Asociando un <xref:System.Windows.Forms.ContextMenuStrip> componente con la persona <xref:System.Windows.Forms.TreeNode> elementos, puede agregar un nivel de funcionalidad del menú contextual para personalizado su <xref:System.Windows.Forms.TreeView> controles.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Para asociar un menú contextual a un objeto TreeNode mediante programación  
  
1.  Crear una instancia de un <xref:System.Windows.Forms.TreeView> controlar con la configuración de la propiedad adecuada, cree una raíz <xref:System.Windows.Forms.TreeNode>y, a continuación, agregue los subnodos.  
  
2.  Crear una instancia de un <xref:System.Windows.Forms.ContextMenuStrip> componente y, a continuación, agregue un <xref:System.Windows.Forms.ToolStripMenuItem> para cada operación que desea que estén disponibles en tiempo de ejecución.  
  
3.  Establecer el <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> propiedad de adecuado <xref:System.Windows.Forms.TreeNode> en el menú contextual que cree.  
  
4.  Cuando se establece esta propiedad, se mostrará el menú contextual cuando hace clic en el nodo.  
  
 En el ejemplo de código siguiente se crea un basic <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ContextMenuStrip> asociada a la raíz <xref:System.Windows.Forms.TreeNode> de la <xref:System.Windows.Forms.TreeView>. Debe personalizar las opciones de menú a los que se ajusten a la <xref:System.Windows.Forms.TreeView> está desarrollando. Además, desea escribir código para controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para estos elementos de menú.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ContextMenuStrip>
- [TreeView (Control)](treeview-control-windows-forms.md)
