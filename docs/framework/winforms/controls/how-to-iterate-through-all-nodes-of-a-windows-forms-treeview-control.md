---
title: Recorrer en iteración todos los nodos del control TreeView
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
ms.openlocfilehash: 010932fa3fdfaa907325b9934682dcbf889265c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736368"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>Cómo: Recorrer en iteración todos los nodos del control TreeView de Windows Forms
A veces resulta útil examinar todos los nodos de un Windows Forms <xref:System.Windows.Forms.TreeView> control para realizar algún cálculo en los valores de nodo. Esta operación puede realizarse mediante un procedimiento recursivo (un método recursivo en C# y C++) que recorre en iteración los nodos de cada colección del árbol.  
  
 Cada <xref:System.Windows.Forms.TreeNode> objeto de una vista de árbol tiene propiedades que puede usar para navegar por la vista de árbol: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>y <xref:System.Windows.Forms.TreeNode.Parent%2A>. El valor de la propiedad <xref:System.Windows.Forms.TreeNode.Parent%2A> es el nodo primario del nodo actual. Los nodos secundarios del nodo actual, si hay alguno, se enumeran en su <xref:System.Windows.Forms.TreeNode.Nodes%2A> propiedad. El propio control <xref:System.Windows.Forms.TreeView> tiene la propiedad <xref:System.Windows.Forms.TreeView.TopNode%2A>, que es el nodo raíz de la vista de árbol completa.  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>Para recorrer en iteración todos los nodos del control TreeView  
  
1. Cree un procedimiento recursivo (un método recursivo en C# y C++) que compruebe cada nodo.  
  
2. Llame al procedimiento.  
  
     En el ejemplo siguiente se muestra cómo imprimir la propiedad <xref:System.Windows.Forms.TreeNode.Text%2A> de cada <xref:System.Windows.Forms.TreeNode> objeto:  
  
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
  
## <a name="see-also"></a>Vea también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
