---
title: Procedimiento Agregar y quitar nodos con el Control TreeView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 30dbe55711d92ea1fdbbbfd147a65b27d0dc9a50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711514"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Procedimiento Agregar y quitar nodos con el Control TreeView de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.TreeView> control almacena los nodos de nivel superior en su <xref:System.Windows.Forms.TreeView.Nodes%2A> colección. Cada <xref:System.Windows.Forms.TreeNode> también tiene su propio <xref:System.Windows.Forms.TreeNode.Nodes%2A> colección para almacenar sus nodos secundarios. Ambas propiedades de colección son del tipo <xref:System.Windows.Forms.TreeNodeCollection>, que proporciona los miembros de colección estándar que permiten agregar, eliminar y reorganizar los nodos de un solo nivel de la jerarquía de nodos.  
  
### <a name="to-add-nodes-programmatically"></a>Para agregar nodos mediante programación  
  
1.  Use la <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> método de la vista de árbol <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Para quitar los nodos mediante programación  
  
1.  Use la <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> método de la vista de árbol <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad que se va a quitar un solo nodo, o el <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> método para borrar todos los nodos.  
  
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
  
## <a name="see-also"></a>Vea también
- [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [Cómo: Establecer iconos para el Control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
