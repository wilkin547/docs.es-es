---
title: "C&#243;mo: Recorrer en iteraci&#243;n todos los nodos del control TreeView de formularios Windows Forms | Microsoft Docs"
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
  - "nodos de árbol en el control TreeView, recorrer en iteración"
  - "TreeView (control) [Windows Forms], recorrer nodos en iteración"
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Recorrer en iteraci&#243;n todos los nodos del control TreeView de formularios Windows Forms
En ocasiones es útil examinar todos los nodos de un control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms para ejecutar ciertos cálculos sobre los valores de los nodos.  Esta operación puede realizarse por medio de un procedimiento recursivo \(un método recursivo en C\# y C\+\+\) que recorra en iteración los nodos de cada colección del árbol.  
  
 Cada objeto <xref:System.Windows.Forms.TreeNode> de una vista de árbol tiene propiedades que puede utilizar para navegar por la vista de árbol: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A> y <xref:System.Windows.Forms.TreeNode.Parent%2A>.  El valor de la propiedad <xref:System.Windows.Forms.TreeNode.Parent%2A> es el nodo principal del nodo actual.  Los nodos secundarios del nodo actual, si existen, se enumeran en su propiedad <xref:System.Windows.Forms.TreeNode.Nodes%2A>.  El propio control <xref:System.Windows.Forms.TreeView> dispone de la propiedad <xref:System.Windows.Forms.TreeView.TopNode%2A>, que es el nodo raíz de toda la vista de árbol.  
  
### Para recorrer en iteración todos los nodos del control TreeView  
  
1.  Cree un procedimiento recursivo \(un método recursivo en C\# y C\+\+\) que compruebe cada nodo.  
  
2.  Llame al procedimiento.  
  
     En el ejemplo siguiente se muestra cómo imprimir la propiedad <xref:System.Windows.Forms.TreeNode.Text%2A> de cada objeto <xref:System.Windows.Forms.TreeNode>:  
  
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
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Procedimientos recursivos](../Topic/Recursive%20Procedures%20\(Visual%20Basic\).md)