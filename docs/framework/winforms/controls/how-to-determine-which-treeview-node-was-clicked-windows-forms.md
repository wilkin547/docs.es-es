---
title: 'Cómo: Determinar en qué nodo de TreeView se hizo clic (formularios Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: d1e9df6a928f1ea60e4663c78d204ec2b16baf23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530632"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Cómo: Determinar en qué nodo de TreeView se hizo clic (formularios Windows Forms)
Al trabajar con formularios Windows Forms <xref:System.Windows.Forms.TreeView> (control), una tarea común es determinar qué nodo se hizo clic y responder según corresponda.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Para determinar qué nodo de TreeView se hizo clic  
  
1.  Use la <xref:System.EventArgs> objeto para devolver una referencia al objeto de nodo donde ha hecho clic.  
  
2.  Determinar en qué nodo se hizo clic comprobando la <xref:System.Windows.Forms.TreeViewEventArgs> (clase), que contiene los datos relacionados con el evento.  
  
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
    >  Como alternativa, puede utilizar el <xref:System.Windows.Forms.MouseEventArgs> de la <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> eventos para obtener el <xref:System.Drawing.Point.X%2A> y <xref:System.Drawing.Point.Y%2A> coordinar los valores de la <xref:System.Drawing.Point> en el que hizo clic. A continuación, utilice la <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> método para determinar qué nodo se hizo clic.  
  
## <a name="see-also"></a>Vea también  
 [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
