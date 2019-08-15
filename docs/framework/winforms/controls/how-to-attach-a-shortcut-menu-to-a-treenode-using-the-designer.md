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
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Procedimiento para adjuntar un menú contextual a un objeto TreeNode mediante el diseñador
El control <xref:System.Windows.Forms.TreeView> Windows Forms muestra una jerarquía de nodos, similar a los archivos y carpetas que se muestran en el panel izquierdo de la característica explorador de Windows en los sistemas operativos Windows. Al establecer la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando hace clic con el botón secundario en <xref:System.Windows.Forms.TreeView> el control. Al asociar un <xref:System.Windows.Forms.ContextMenuStrip> componente a elementos <xref:System.Windows.Forms.TreeNode> individuales, puede Agregar un nivel personalizado de funcionalidad de menú contextual a <xref:System.Windows.Forms.TreeView> los controles.

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Para asociar un menú contextual con un TreeNode en tiempo de diseño

1. Agregue un <xref:System.Windows.Forms.TreeView> control al formulario y, a continuación, agregue los <xref:System.Windows.Forms.TreeView> nodos al según sea necesario. Para obtener más información, consulte [Cómo Agregue y quite nodos con el control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)TreeView Windows Forms.

2. Agregue un <xref:System.Windows.Forms.ContextMenuStrip> componente al formulario y, a continuación, agregue los elementos de menú al menú contextual que representan las operaciones de nivel de nodo que desea que estén disponibles en tiempo de ejecución. Para obtener más información, consulte [Cómo Agregar elementos de menú a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).

3. Vuelva a abrir el cuadro de diálogo TreeNodeEditor <xref:System.Windows.Forms.TreeView> para el control, seleccione el nodo que desea editar y <xref:System.Windows.Forms.ContextMenuStrip> establezca su propiedad en el menú contextual que ha agregado.

4. Cuando se establece esta propiedad, el menú contextual se muestra cuando se hace clic con el botón secundario en el nodo.

     Además, querrá escribir código para controlar los <xref:System.Windows.Forms.ToolStripItem.Click> eventos de estos elementos de menú.

## <a name="see-also"></a>Vea también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [ContextMenuStrip (Control)](contextmenustrip-control.md)
