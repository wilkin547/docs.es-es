---
title: Agregar y quitar nodos con el control TreeView
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
ms.openlocfilehash: 02b3a7286798c6f2a6426e09c8fc6c18b74a6bf0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731959"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Cómo: Agregar y quitar nodos con el control TreeView de Windows Forms
El control <xref:System.Windows.Forms.TreeView> de Windows Forms almacena los nodos de nivel superior en su colección <xref:System.Windows.Forms.TreeView.Nodes%2A>. Cada <xref:System.Windows.Forms.TreeNode> tiene también su propia colección <xref:System.Windows.Forms.TreeNode.Nodes%2A> para almacenar sus nodos secundarios. Ambas propiedades de colección son del tipo <xref:System.Windows.Forms.TreeNodeCollection>, que proporciona miembros de colección estándar que permiten agregar, quitar y reorganizar los nodos en un solo nivel de la jerarquía de nodos.  
  
### <a name="to-add-nodes-programmatically"></a>Para agregar nodos mediante programación  
  
1. Use el método <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista de árbol.  
  
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
  
1. Utilice el método <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista de árbol para quitar un solo nodo o el método <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> para borrar todos los nodos.  
  
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
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Establecer iconos del control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
