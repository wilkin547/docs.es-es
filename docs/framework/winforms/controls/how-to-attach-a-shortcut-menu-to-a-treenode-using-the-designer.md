---
title: Procedimiento Asociar un menú contextual para un objeto TreeNode mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 6b98523b7422e87e70b9d786f061869d1ab4523e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566962"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Procedimiento Asociar un menú contextual para un objeto TreeNode mediante el diseñador
Los formularios de Windows <xref:System.Windows.Forms.TreeView> control muestra una jerarquía de nodos, similares a los archivos y carpetas que se muestran en el panel izquierdo de la característica Explorador de Windows en sistemas operativos de Windows. Estableciendo el <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad, puede proporcionar operaciones contextuales al usuario cuando haga clic en el <xref:System.Windows.Forms.TreeView> control. Asociando un <xref:System.Windows.Forms.ContextMenuStrip> componente con la persona <xref:System.Windows.Forms.TreeNode> elementos, puede agregar un nivel de funcionalidad del menú contextual para personalizado su <xref:System.Windows.Forms.TreeView> controles.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Para asociar un menú contextual a un objeto TreeNode en tiempo de diseño  
  
1.  Agregar un <xref:System.Windows.Forms.TreeView> control al formulario y, a continuación, agregar nodos a la <xref:System.Windows.Forms.TreeView> según sea necesario. Para obtener más información, vea [Cómo: Agregar y quitar nodos con el Windows Forms Control TreeView](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Agregar un <xref:System.Windows.Forms.ContextMenuStrip> al formulario y, a continuación, agregar elementos de menú al menú contextual que representan las operaciones de nivel de nodo que desea que estén disponibles en tiempo de ejecución. Para obtener más información, vea [Cómo: Agregar elementos de menú a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Vuelva a abrir el **TreeNodeEditor** cuadro de diálogo para la <xref:System.Windows.Forms.TreeView> de control, seleccione el nodo para editar y establezca su <xref:System.Windows.Forms.ContextMenuStrip> propiedad en el menú contextual que agregó.  
  
4.  Cuando se establece esta propiedad, se mostrará el menú contextual cuando hace clic en el nodo.  
  
     Además, desea escribir código para controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para estos elementos de menú.  
  
## <a name="see-also"></a>Vea también
- [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [ContextMenuStrip (Control)](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
