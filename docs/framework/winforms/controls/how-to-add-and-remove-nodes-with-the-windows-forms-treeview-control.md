---
title: "C&#243;mo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], TreeView (control)"
  - "nodos de árbol en el control TreeView"
  - "TreeView (control) [Windows Forms], agregar nodos"
  - "TreeView (control) [Windows Forms], quitar nodos"
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms
El control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms almacena los nodos de nivel superior en su colección <xref:System.Windows.Forms.TreeView.Nodes%2A>.  Cada <xref:System.Windows.Forms.TreeNode> tiene también su propia colección <xref:System.Windows.Forms.TreeNode.Nodes%2A> para almacenar sus nodos secundarios.  Ambas propiedades de colección son de tipo <xref:System.Windows.Forms.TreeNodeCollection>, lo que proporciona miembros de colección estándar que permiten agregar, quitar y reorganizar los nodos en un solo nivel de la jerarquía de nodos.  
  
### Para agregar nodos mediante programación  
  
1.  Utilice el método <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista del árbol.  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### Para quitar nodos mediante programación  
  
1.  Utilice el método <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista del árbol para quitar un solo nodo, o el método <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> para borrarlos todos.  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Cómo: Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Cómo: Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Cómo: Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)