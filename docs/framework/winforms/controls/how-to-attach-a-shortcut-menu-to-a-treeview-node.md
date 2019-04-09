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
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="2c33b-102">Filtrar para asociar un menú contextual a un nodo TreeView</span><span class="sxs-lookup"><span data-stu-id="2c33b-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="2c33b-103">Los formularios de Windows <xref:System.Windows.Forms.TreeView> control muestra una jerarquía de nodos, similares a los archivos y carpetas que se muestra en el panel izquierdo del explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="2c33b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="2c33b-104">Estableciendo el <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando haga clic en el <xref:System.Windows.Forms.TreeView> control.</span><span class="sxs-lookup"><span data-stu-id="2c33b-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="2c33b-105">Asociando un <xref:System.Windows.Forms.ContextMenuStrip> componente con la persona <xref:System.Windows.Forms.TreeNode> elementos, puede agregar un nivel de funcionalidad del menú contextual para personalizado su <xref:System.Windows.Forms.TreeView> controles.</span><span class="sxs-lookup"><span data-stu-id="2c33b-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="2c33b-106">Para asociar un menú contextual a un objeto TreeNode mediante programación</span><span class="sxs-lookup"><span data-stu-id="2c33b-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="2c33b-107">Crear una instancia de un <xref:System.Windows.Forms.TreeView> controlar con la configuración de la propiedad adecuada, cree una raíz <xref:System.Windows.Forms.TreeNode>y, a continuación, agregue los subnodos.</span><span class="sxs-lookup"><span data-stu-id="2c33b-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="2c33b-108">Crear una instancia de un <xref:System.Windows.Forms.ContextMenuStrip> componente y, a continuación, agregue un <xref:System.Windows.Forms.ToolStripMenuItem> para cada operación que desea que estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c33b-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="2c33b-109">Establecer el <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> propiedad de adecuado <xref:System.Windows.Forms.TreeNode> en el menú contextual que cree.</span><span class="sxs-lookup"><span data-stu-id="2c33b-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="2c33b-110">Cuando se establece esta propiedad, se mostrará el menú contextual cuando hace clic en el nodo.</span><span class="sxs-lookup"><span data-stu-id="2c33b-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="2c33b-111">En el ejemplo de código siguiente se crea un basic <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ContextMenuStrip> asociada a la raíz <xref:System.Windows.Forms.TreeNode> de la <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="2c33b-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="2c33b-112">Debe personalizar las opciones de menú a los que se ajusten a la <xref:System.Windows.Forms.TreeView> está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="2c33b-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="2c33b-113">Además, desea escribir código para controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para estos elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="2c33b-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2c33b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c33b-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="2c33b-115">TreeView (Control)</span><span class="sxs-lookup"><span data-stu-id="2c33b-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
