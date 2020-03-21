---
title: 'Cómo: Determinar en qué nodo de TreeView se hizo clic'
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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182185"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Cómo: Determinar en qué nodo de TreeView se hizo clic (formularios Windows Forms)
Cuando se trabaja <xref:System.Windows.Forms.TreeView> con el control de formularios Windows Forms, una tarea común es determinar en qué nodo se hizo clic y responder adecuadamente.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Para determinar qué nodo TreeView se ha en clic  
  
1. Utilice <xref:System.EventArgs> el objeto para devolver una referencia al objeto de nodo en el que se ha clic.  
  
2. Determine en qué nodo se <xref:System.Windows.Forms.TreeViewEventArgs> ha haciendo clic comprobando la clase, que contiene datos relacionados con el evento.  
  
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
    > Como alternativa, puede utilizar <xref:System.Windows.Forms.MouseEventArgs> el <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> evento o <xref:System.Drawing.Point.X%2A> para <xref:System.Drawing.Point.Y%2A> obtener los <xref:System.Drawing.Point> valores de coordenadas y del lugar donde se produjo el clic. A continuación, <xref:System.Windows.Forms.TreeView> utilice <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> el método del control para determinar en qué nodo se hizo clic.  
  
## <a name="see-also"></a>Consulte también

- [TreeView (control)](treeview-control-windows-forms.md)
