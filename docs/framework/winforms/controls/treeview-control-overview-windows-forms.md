---
title: "Informaci&#243;n general del control TreeView (Formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TreeView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "TreeView (control) [Windows Forms], acerca del control TreeView"
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general del control TreeView (Formularios Windows Forms)
Con el control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar una jerarquía de nodos a los usuarios, por ejemplo, la forma en que los archivos y las carpetas se muestran en el panel izquierdo de la característica Explorador de Windows del sistema operativo Windows.  Cada nodo de la vista de árbol puede contener otros nodos, llamados *nodos secundarios*.  Los nodos primarios, o nodos que contienen nodos secundarios, se pueden mostrar expandidos o contraídos.  También puede mostrar una vista de árbol con casillas junto a los nodos estableciendo la propiedad <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> de la vista de árbol en `true`.  Después, puede activar o desactivar nodos configurando mediante programación la propiedad <xref:System.Windows.Forms.TreeNode.Checked%2A> del nodo en `true` o `false`.  
  
## Propiedades clave  
 Las propiedades clave del control <xref:System.Windows.Forms.TreeView> son <xref:System.Windows.Forms.TreeView.Nodes%2A> y <xref:System.Windows.Forms.TreeView.SelectedNode%2A>.  La propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> contiene la lista de nodos de nivel superior de la vista de árbol.  La propiedad <xref:System.Windows.Forms.TreeView.SelectedNode%2A> establece el nodo actualmente seleccionado.  Puede mostrar iconos junto a los nodos.  El control usa las imágenes de la <xref:System.Windows.Forms.ImageList> con nombre en la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> de la vista de árbol.  La propiedad <xref:System.Windows.Forms.TreeView.ImageIndex%2A> establece la imagen predeterminada de los nodos en la vista de árbol.  Para obtener más información acerca de cómo mostrar imágenes, consulte [Cómo: Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md).  Si está usando [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el control <xref:System.Windows.Forms.TreeView>.  
  
## Vea también  
 <xref:System.Windows.Forms.TreeView>   
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Cómo: Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Cómo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Cómo: Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Cómo: Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)