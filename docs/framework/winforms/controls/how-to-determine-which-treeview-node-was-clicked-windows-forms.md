---
title: Procedimiento Determinar qué nodo de TreeView se hizo clic (formularios Windows Forms)
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
ms.openlocfilehash: 802367c26562d1b5aaf2398ed122cb97afbff255
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580117"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedimiento Determinar qué nodo de TreeView se hizo clic (formularios Windows Forms)
Cuando se trabaja con los formularios de Windows <xref:System.Windows.Forms.TreeView> control, es una tarea común determinar qué nodo se hizo clic y responder según corresponda.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Para determinar qué nodo de TreeView se hizo clic  
  
1.  Use la <xref:System.EventArgs> objeto para devolver una referencia al objeto de nodo donde ha hecho clic.  
  
2.  Determinar qué nodo se hizo clic mediante la comprobación de la <xref:System.Windows.Forms.TreeViewEventArgs> (clase), que contiene los datos relacionados con el evento.  
  
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
    >  Como alternativa, puede usar el <xref:System.Windows.Forms.MouseEventArgs> de la <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> eventos para obtener el <xref:System.Drawing.Point.X%2A> y <xref:System.Drawing.Point.Y%2A> coordinar los valores de la <xref:System.Drawing.Point> donde se hizo clic. A continuación, utilice el <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> método para determinar qué nodo se hizo clic.  
  
## <a name="see-also"></a>Vea también
- [TreeView (control)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
