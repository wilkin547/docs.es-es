---
title: Agregar y quitar nodos con TreeView Control
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
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142217"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Cómo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms
El control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms <xref:System.Windows.Forms.TreeView.Nodes%2A> almacena los nodos de nivel superior de su colección. Cada <xref:System.Windows.Forms.TreeNode> uno también <xref:System.Windows.Forms.TreeNode.Nodes%2A> tiene su propia colección para almacenar sus nodos secundarios. Ambas propiedades de <xref:System.Windows.Forms.TreeNodeCollection>colección son de tipo , que proporciona miembros de colección estándar que le permiten agregar, quitar y reorganizar los nodos en un único nivel de la jerarquía de nodos.  
  
### <a name="to-add-nodes-programmatically"></a>Para agregar nodos mediante programación  
  
1. Utilice <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> el método de la <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad de la vista de árbol.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Para quitar nodos mediante programación  
  
1. Utilice <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> el método de la <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad de la vista de <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> árbol para quitar un único nodo o el método para borrar todos los nodos.  
  
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
  
## <a name="see-also"></a>Consulte también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Información general sobre el control TreeView](treeview-control-overview-windows-forms.md)
- [Establecer iconos del control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
