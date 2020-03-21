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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="b3faf-102">Cómo: Determinar en qué nodo de TreeView se hizo clic (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b3faf-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="b3faf-103">Cuando se trabaja <xref:System.Windows.Forms.TreeView> con el control de formularios Windows Forms, una tarea común es determinar en qué nodo se hizo clic y responder adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="b3faf-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="b3faf-104">Para determinar qué nodo TreeView se ha en clic</span><span class="sxs-lookup"><span data-stu-id="b3faf-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="b3faf-105">Utilice <xref:System.EventArgs> el objeto para devolver una referencia al objeto de nodo en el que se ha clic.</span><span class="sxs-lookup"><span data-stu-id="b3faf-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="b3faf-106">Determine en qué nodo se <xref:System.Windows.Forms.TreeViewEventArgs> ha haciendo clic comprobando la clase, que contiene datos relacionados con el evento.</span><span class="sxs-lookup"><span data-stu-id="b3faf-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="b3faf-107">Como alternativa, puede utilizar <xref:System.Windows.Forms.MouseEventArgs> el <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> evento o <xref:System.Drawing.Point.X%2A> para <xref:System.Drawing.Point.Y%2A> obtener los <xref:System.Drawing.Point> valores de coordenadas y del lugar donde se produjo el clic.</span><span class="sxs-lookup"><span data-stu-id="b3faf-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="b3faf-108">A continuación, <xref:System.Windows.Forms.TreeView> utilice <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> el método del control para determinar en qué nodo se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="b3faf-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3faf-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3faf-109">See also</span></span>

- [<span data-ttu-id="b3faf-110">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="b3faf-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
