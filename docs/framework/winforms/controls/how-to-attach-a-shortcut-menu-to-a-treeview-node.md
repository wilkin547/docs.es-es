---
title: "Cómo: Asociar un menú contextual a un nodo TreeView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d3814e95ad2d91157181682984fc9b53254ba813
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="42d0a-102">Cómo: Asociar un menú contextual a un nodo TreeView</span><span class="sxs-lookup"><span data-stu-id="42d0a-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="42d0a-103">Los formularios Windows Forms <xref:System.Windows.Forms.TreeView> control muestra una jerarquía de nodos, similares a los archivos y las carpetas que aparecen en el panel izquierdo del explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="42d0a-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="42d0a-104">Estableciendo la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando haga clic en el <xref:System.Windows.Forms.TreeView> control.</span><span class="sxs-lookup"><span data-stu-id="42d0a-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="42d0a-105">Asociando un <xref:System.Windows.Forms.ContextMenuStrip> componente de individual <xref:System.Windows.Forms.TreeNode> elementos, puede agregar un nivel personalizado de funcionalidad del menú contextual para su <xref:System.Windows.Forms.TreeView> controles.</span><span class="sxs-lookup"><span data-stu-id="42d0a-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="42d0a-106">Para asociar un menú contextual a un objeto TreeNode mediante programación</span><span class="sxs-lookup"><span data-stu-id="42d0a-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="42d0a-107">Crear una instancia de un <xref:System.Windows.Forms.TreeView> controlar con la configuración de la propiedad adecuada, cree una raíz <xref:System.Windows.Forms.TreeNode>y, a continuación, agregue los subnodos.</span><span class="sxs-lookup"><span data-stu-id="42d0a-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="42d0a-108">Crear una instancia de un <xref:System.Windows.Forms.ContextMenuStrip> componente y, a continuación, agregue un <xref:System.Windows.Forms.ToolStripMenuItem> para cada operación que desee que estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="42d0a-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="42d0a-109">Establecer el <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> propiedad de los <xref:System.Windows.Forms.TreeNode> en el menú contextual que cree.</span><span class="sxs-lookup"><span data-stu-id="42d0a-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="42d0a-110">Cuando se establece esta propiedad, se mostrará el menú contextual cuando haga clic en el nodo.</span><span class="sxs-lookup"><span data-stu-id="42d0a-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="42d0a-111">En el ejemplo de código siguiente se crea un basic <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ContextMenuStrip> asociado a la raíz <xref:System.Windows.Forms.TreeNode> de la <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="42d0a-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="42d0a-112">Debe personalizar las opciones de menú a los que se ajusten a los <xref:System.Windows.Forms.TreeView> que está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="42d0a-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="42d0a-113">Además, desea escribir código para controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para estos elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="42d0a-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="42d0a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="42d0a-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="42d0a-115">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="42d0a-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
