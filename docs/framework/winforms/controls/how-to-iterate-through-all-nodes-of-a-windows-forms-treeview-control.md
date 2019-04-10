---
title: Filtrar para iterar todos los nodos del control TreeView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 4b287cecddd63ec6535feb70118c3466c8960531
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314235"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="560e5-102">Filtrar para iterar todos los nodos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="560e5-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>
<span data-ttu-id="560e5-103">A veces es útil examinar todos los nodos en un formulario Windows Forms <xref:System.Windows.Forms.TreeView> control con el fin de realizar algún cálculo en los valores de nodo.</span><span class="sxs-lookup"><span data-stu-id="560e5-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="560e5-104">Esta operación puede realizarse mediante un procedimiento recursivo (un método recursivo en C# y C++) que recorre en iteración los nodos de cada colección del árbol.</span><span class="sxs-lookup"><span data-stu-id="560e5-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="560e5-105">Cada <xref:System.Windows.Forms.TreeNode> objeto en una vista de árbol tiene propiedades que puede usar para navegar por la vista de árbol: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, y <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span><span class="sxs-lookup"><span data-stu-id="560e5-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="560e5-106">El valor de la <xref:System.Windows.Forms.TreeNode.Parent%2A> propiedad es el nodo primario del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="560e5-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="560e5-107">Los nodos secundarios del nodo actual, si existe alguna, se muestran en su <xref:System.Windows.Forms.TreeNode.Nodes%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="560e5-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="560e5-108">El <xref:System.Windows.Forms.TreeView> propio control tiene el <xref:System.Windows.Forms.TreeView.TopNode%2A> propiedad, que es el nodo raíz de la vista de árbol completa.</span><span class="sxs-lookup"><span data-stu-id="560e5-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="560e5-109">Para recorrer en iteración todos los nodos del control TreeView</span><span class="sxs-lookup"><span data-stu-id="560e5-109">To iterate through all nodes of the TreeView control</span></span>  
  
1. <span data-ttu-id="560e5-110">Cree un procedimiento recursivo (un método recursivo en C# y C++) que compruebe cada nodo.</span><span class="sxs-lookup"><span data-stu-id="560e5-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2. <span data-ttu-id="560e5-111">Llame al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="560e5-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="560e5-112">El ejemplo siguiente muestra cómo imprimir cada <xref:System.Windows.Forms.TreeNode> del objeto <xref:System.Windows.Forms.TreeNode.Text%2A> propiedad:</span><span class="sxs-lookup"><span data-stu-id="560e5-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="560e5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="560e5-113">See also</span></span>

- [<span data-ttu-id="560e5-114">TreeView (Control)</span><span class="sxs-lookup"><span data-stu-id="560e5-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="560e5-115">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="560e5-115">Recursive Procedures</span></span>](~/docs/visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
