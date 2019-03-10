---
title: Filtrar Agregar y quitar nodos con el Control TreeView de formularios Windows Forms
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
ms.openlocfilehash: d0a77f55e28055ef097f0b4604c316f7751abdbe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702690"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="b2c33-102">Procedimiento Agregar y quitar nodos con el Control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2c33-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="b2c33-103">Los formularios de Windows <xref:System.Windows.Forms.TreeView> control almacena los nodos de nivel superior en su <xref:System.Windows.Forms.TreeView.Nodes%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="b2c33-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="b2c33-104">Cada <xref:System.Windows.Forms.TreeNode> también tiene su propio <xref:System.Windows.Forms.TreeNode.Nodes%2A> colección para almacenar sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b2c33-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="b2c33-105">Ambas propiedades de colección son del tipo <xref:System.Windows.Forms.TreeNodeCollection>, que proporciona los miembros de colección estándar que permiten agregar, eliminar y reorganizar los nodos de un solo nivel de la jerarquía de nodos.</span><span class="sxs-lookup"><span data-stu-id="b2c33-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="b2c33-106">Para agregar nodos mediante programación</span><span class="sxs-lookup"><span data-stu-id="b2c33-106">To add nodes programmatically</span></span>  
  
1.  <span data-ttu-id="b2c33-107">Use la <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> método de la vista de árbol <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b2c33-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="b2c33-108">Para quitar los nodos mediante programación</span><span class="sxs-lookup"><span data-stu-id="b2c33-108">To remove nodes programmatically</span></span>  
  
1.  <span data-ttu-id="b2c33-109">Use la <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> método de la vista de árbol <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad que se va a quitar un solo nodo, o el <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> método para borrar todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="b2c33-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2c33-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c33-110">See also</span></span>
- [<span data-ttu-id="b2c33-111">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="b2c33-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="b2c33-112">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="b2c33-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="b2c33-113">Cómo: Establecer iconos para el Control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2c33-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="b2c33-114">Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2c33-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="b2c33-115">Cómo: Determinar qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="b2c33-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="b2c33-116">Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b2c33-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
