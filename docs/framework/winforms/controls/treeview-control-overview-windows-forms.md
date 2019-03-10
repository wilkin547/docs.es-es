---
title: Información general del control TreeView (Formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: 046713745e7de18cefe5b4883af73034af2cfb31
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712033"
---
# <a name="treeview-control-overview-windows-forms"></a>Información general del control TreeView (Formularios Windows Forms)

Con el control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar una jerarquía de nodos a los usuarios, por ejemplo, la forma en que los archivos y las carpetas se muestran en el panel izquierdo de la característica Explorador de Windows del sistema operativo Windows. Cada nodo en la vista de árbol puede contener otros nodos, llamados *nodos secundarios*. Los nodos primarios, o nodos que contienen nodos secundarios, se pueden mostrar expandidos o contraídos. También puede mostrar una vista de árbol con casillas junto a los nodos estableciendo la propiedad <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> de la vista de árbol en `true`. Después, puede activar o desactivar nodos configurando mediante programación la propiedad <xref:System.Windows.Forms.TreeNode.Checked%2A> del nodo en `true` o `false`.

## <a name="key-properties"></a>Propiedades clave

Las propiedades clave del control <xref:System.Windows.Forms.TreeView> son <xref:System.Windows.Forms.TreeView.Nodes%2A> y <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. La propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> contiene la lista de nodos de nivel superior de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.SelectedNode%2A> establece el nodo actualmente seleccionado. Puede mostrar iconos junto a los nodos. El control usa las imágenes de la <xref:System.Windows.Forms.ImageList> con nombre en la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.ImageIndex%2A> establece la imagen predeterminada de los nodos en la vista de árbol. Para obtener más información acerca de cómo mostrar imágenes, vea [Cómo: Establecer iconos para los Windows Forms Control TreeView](how-to-set-icons-for-the-windows-forms-treeview-control.md). Si utiliza Visual Studio 2005, tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el <xref:System.Windows.Forms.TreeView> control.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TreeView>
- [TreeView (control)](treeview-control-windows-forms.md)
- [Cómo: Establecer iconos para el Control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Cómo: Agregar y quitar nodos con el Control TreeView de formularios Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)