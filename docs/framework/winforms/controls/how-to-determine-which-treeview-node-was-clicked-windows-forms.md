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
ms.openlocfilehash: 71f13c7b160822c92475d4d03e923b40d4f0454d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771051"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="0b443-102">Procedimiento Determinar qué nodo de TreeView se hizo clic (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0b443-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="0b443-103">Cuando se trabaja con los formularios de Windows <xref:System.Windows.Forms.TreeView> control, es una tarea común determinar qué nodo se hizo clic y responder según corresponda.</span><span class="sxs-lookup"><span data-stu-id="0b443-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="0b443-104">Para determinar qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="0b443-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="0b443-105">Use la <xref:System.EventArgs> objeto para devolver una referencia al objeto de nodo donde ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="0b443-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="0b443-106">Determinar qué nodo se hizo clic mediante la comprobación de la <xref:System.Windows.Forms.TreeViewEventArgs> (clase), que contiene los datos relacionados con el evento.</span><span class="sxs-lookup"><span data-stu-id="0b443-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    >  <span data-ttu-id="0b443-107">Como alternativa, puede usar el <xref:System.Windows.Forms.MouseEventArgs> de la <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> eventos para obtener el <xref:System.Drawing.Point.X%2A> y <xref:System.Drawing.Point.Y%2A> coordinar los valores de la <xref:System.Drawing.Point> donde se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="0b443-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="0b443-108">A continuación, utilice el <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> método para determinar qué nodo se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="0b443-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b443-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b443-109">See also</span></span>

- [<span data-ttu-id="0b443-110">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="0b443-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
