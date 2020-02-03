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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="dc21a-102">Cómo: Agregar y quitar nodos con el control TreeView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc21a-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="dc21a-103">El control <xref:System.Windows.Forms.TreeView> de Windows Forms almacena los nodos de nivel superior en su colección <xref:System.Windows.Forms.TreeView.Nodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc21a-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="dc21a-104">Cada <xref:System.Windows.Forms.TreeNode> tiene también su propia colección <xref:System.Windows.Forms.TreeNode.Nodes%2A> para almacenar sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="dc21a-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="dc21a-105">Ambas propiedades de colección son del tipo <xref:System.Windows.Forms.TreeNodeCollection>, que proporciona miembros de colección estándar que permiten agregar, quitar y reorganizar los nodos en un solo nivel de la jerarquía de nodos.</span><span class="sxs-lookup"><span data-stu-id="dc21a-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="dc21a-106">Para agregar nodos mediante programación</span><span class="sxs-lookup"><span data-stu-id="dc21a-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="dc21a-107">Use el método <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="dc21a-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="dc21a-108">Para quitar nodos mediante programación</span><span class="sxs-lookup"><span data-stu-id="dc21a-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="dc21a-109">Utilice el método <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> de la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> de la vista de árbol para quitar un solo nodo o el método <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> para borrar todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="dc21a-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc21a-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc21a-110">See also</span></span>

- [<span data-ttu-id="dc21a-111">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="dc21a-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="dc21a-112">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="dc21a-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="dc21a-113">Establecer iconos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc21a-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="dc21a-114">Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc21a-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="dc21a-115">Determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="dc21a-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="dc21a-116">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dc21a-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
