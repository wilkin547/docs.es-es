---
title: 'Cómo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 95f3f097d8e01828f2727bac742c752b656019e5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44047642"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Cómo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Diseñador
Dado que los Windows Forms <xref:System.Windows.Forms.TreeView> control muestra los nodos de forma jerárquica, al agregar un nodo que debe prestar atención a lo que es su nodo primario.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.TreeView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>Para agregar o quitar nodos en el diseñador  
  
1.  Seleccione el control <xref:System.Windows.Forms.TreeView>.  
  
2.  En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) situado junto a el <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad.  
  
     El **Editor TreeNode** aparece.  
  
3.  Para agregar nodos, debe existir un nodo raíz; Si no existe, primero debe agregar una raíz, haga clic en el **Agregar raíz** botón. A continuación, puede agregar nodos secundarios, seleccione la raíz o cualquier otro nodo y haga clic en el **agregar secundario** botón.  
  
4.  Para eliminar los nodos, seleccione el nodo para eliminar y, a continuación, haga clic en el **eliminar** botón.  
  
## <a name="see-also"></a>Vea también  
 [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
