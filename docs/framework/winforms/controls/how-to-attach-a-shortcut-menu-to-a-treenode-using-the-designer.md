---
title: Procedimiento para adjuntar un menú contextual a un objeto TreeNode mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040445"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="6ca68-102">Procedimiento para adjuntar un menú contextual a un objeto TreeNode mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6ca68-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="6ca68-103">El control <xref:System.Windows.Forms.TreeView> Windows Forms muestra una jerarquía de nodos, similar a los archivos y carpetas que se muestran en el panel izquierdo de la característica explorador de Windows en los sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="6ca68-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="6ca68-104">Al establecer la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando hace clic con el botón secundario en <xref:System.Windows.Forms.TreeView> el control.</span><span class="sxs-lookup"><span data-stu-id="6ca68-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="6ca68-105">Al asociar un <xref:System.Windows.Forms.ContextMenuStrip> componente a elementos <xref:System.Windows.Forms.TreeNode> individuales, puede Agregar un nivel personalizado de funcionalidad de menú contextual a <xref:System.Windows.Forms.TreeView> los controles.</span><span class="sxs-lookup"><span data-stu-id="6ca68-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="6ca68-106">Para asociar un menú contextual con un TreeNode en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="6ca68-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="6ca68-107">Agregue un <xref:System.Windows.Forms.TreeView> control al formulario y, a continuación, agregue los <xref:System.Windows.Forms.TreeView> nodos al según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6ca68-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="6ca68-108">Para obtener más información, consulte [Cómo Agregue y quite nodos con el control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)TreeView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ca68-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="6ca68-109">Agregue un <xref:System.Windows.Forms.ContextMenuStrip> componente al formulario y, a continuación, agregue los elementos de menú al menú contextual que representan las operaciones de nivel de nodo que desea que estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ca68-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="6ca68-110">Para obtener más información, consulte [Cómo Agregar elementos de menú a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span><span class="sxs-lookup"><span data-stu-id="6ca68-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="6ca68-111">Vuelva a abrir el cuadro de diálogo TreeNodeEditor <xref:System.Windows.Forms.TreeView> para el control, seleccione el nodo que desea editar y <xref:System.Windows.Forms.ContextMenuStrip> establezca su propiedad en el menú contextual que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="6ca68-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="6ca68-112">Cuando se establece esta propiedad, el menú contextual se muestra cuando se hace clic con el botón secundario en el nodo.</span><span class="sxs-lookup"><span data-stu-id="6ca68-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="6ca68-113">Además, querrá escribir código para controlar los <xref:System.Windows.Forms.ToolStripItem.Click> eventos de estos elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="6ca68-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ca68-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ca68-114">See also</span></span>

- [<span data-ttu-id="6ca68-115">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="6ca68-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="6ca68-116">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="6ca68-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="6ca68-117">ContextMenuStrip (Control)</span><span class="sxs-lookup"><span data-stu-id="6ca68-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
