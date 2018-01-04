---
title: "Información general del control TreeView (Formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TreeView
helpviewer_keywords: TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bbe8549268c2b67b67184966e938f7d62b766a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="treeview-control-overview-windows-forms"></a>Información general del control TreeView (Formularios Windows Forms)
Con el control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar una jerarquía de nodos a los usuarios, por ejemplo, la forma en que los archivos y las carpetas se muestran en el panel izquierdo de la característica Explorador de Windows del sistema operativo Windows. Cada nodo en la vista de árbol puede contener otros nodos, llamados *nodos secundarios*. Los nodos primarios, o nodos que contienen nodos secundarios, se pueden mostrar expandidos o contraídos. También puede mostrar una vista de árbol con casillas junto a los nodos estableciendo la propiedad <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> de la vista de árbol en `true`. Después, puede activar o desactivar nodos configurando mediante programación la propiedad <xref:System.Windows.Forms.TreeNode.Checked%2A> del nodo en `true` o `false`.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades clave del control <xref:System.Windows.Forms.TreeView> son <xref:System.Windows.Forms.TreeView.Nodes%2A> y <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. La propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> contiene la lista de nodos de nivel superior de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.SelectedNode%2A> establece el nodo actualmente seleccionado. Puede mostrar iconos junto a los nodos. El control usa las imágenes de la <xref:System.Windows.Forms.ImageList> con nombre en la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> de la vista de árbol. La propiedad <xref:System.Windows.Forms.TreeView.ImageIndex%2A> establece la imagen predeterminada de los nodos en la vista de árbol. Para obtener más información acerca de cómo mostrar imágenes, vea [Cómo: establecer iconos para el TreeView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md). Si usa [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el control <xref:System.Windows.Forms.TreeView>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TreeView>  
 [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
