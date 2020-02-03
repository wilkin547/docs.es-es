---
title: Información general del control TreeView
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: 44b5e27273d122f38ea00e009302d427305977a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743224"
---
# <a name="treeview-control-overview-windows-forms"></a>Información general del control TreeView (Formularios Windows Forms)

Con el control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar una jerarquía de nodos a los usuarios, por ejemplo, la forma en que los archivos y las carpetas se muestran en el panel izquierdo de la característica Explorador de Windows del sistema operativo Windows. Cada nodo de la vista de árbol puede contener otros nodos, denominados *nodos secundarios*. Los nodos primarios, o nodos que contienen nodos secundarios, se pueden mostrar expandidos o contraídos. También puede mostrar una vista de árbol con casillas junto a los nodos estableciendo la propiedad <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> de la vista de árbol en `true`. Después, puede activar o desactivar nodos configurando mediante programación la propiedad <xref:System.Windows.Forms.TreeNode.Checked%2A> del nodo en `true` o `false`.

## <a name="key-properties"></a>Propiedades clave

Las propiedades clave del control <xref:System.Windows.Forms.TreeView> son <xref:System.Windows.Forms.TreeView.Nodes%2A> y <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. La propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> contiene la lista de nodos de nivel superior de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.SelectedNode%2A> establece el nodo actualmente seleccionado. Puede mostrar iconos junto a los nodos. El control usa las imágenes de la <xref:System.Windows.Forms.ImageList> con nombre en la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.ImageIndex%2A> establece la imagen predeterminada de los nodos en la vista de árbol. Para obtener más información sobre cómo mostrar imágenes, vea [Cómo: establecer iconos para el control TreeView Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md). Si usa Visual Studio 2005, tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el control de <xref:System.Windows.Forms.TreeView>.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.TreeView>
- [TreeView (control)](treeview-control-windows-forms.md)
- [Establecer iconos del control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Agregar y quitar nodos con el control TreeView de formularios Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
