---
title: "C&#243;mo: Determinar en qu&#233; nodo de TreeView se hizo clic (formularios Windows Forms) | Microsoft Docs"
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
  - "TreeNode"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], TreeView (control)"
  - "nodos de árbol en el control TreeView, determinar en qué nodo se ha hecho clic"
  - "TreeView (control) [Windows Forms], determinar en qué nodo se ha hecho clic"
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Determinar en qu&#233; nodo de TreeView se hizo clic (formularios Windows Forms)
Cuando se trabaja con el control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms, una tarea frecuente es determinar en qué nodo se hizo clic y responder de la manera adecuada.  
  
### Para determinar en qué nodo de TreeView se hizo clic  
  
1.  Utilice el objeto <xref:System.EventArgs> para devolver una referencia al objeto nodo en que se hizo clic.  
  
2.  Determine el nodo en el que se hizo clic comprobando la clase <xref:System.Windows.Forms.TreeViewEventArgs>, que contiene datos relacionados con el evento.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  Como alternativa, puede utilizar <xref:System.Windows.Forms.MouseEventArgs> del evento <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> para obtener los valores de coordenadas <xref:System.Drawing.Point.X%2A> y <xref:System.Drawing.Point.Y%2A> del <xref:System.Drawing.Point> donde se hizo clic.  A continuación, utilice el método <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> del control <xref:System.Windows.Forms.TreeView> para determinar el nodo en el que se hizo clic.  
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)