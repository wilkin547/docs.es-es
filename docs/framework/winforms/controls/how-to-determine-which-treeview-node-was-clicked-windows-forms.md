---
title: Procedimiento Determinar en qué nodo de TreeView se hizo clic (Windows Forms)
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
ms.openlocfilehash: ab93158daf987e2f19516b8fb3abf80bfe79a12c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967344"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="eca2e-102">Procedimiento Determinar en qué nodo de TreeView se hizo clic (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="eca2e-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="eca2e-103">Al trabajar con el control <xref:System.Windows.Forms.TreeView> de Windows Forms, una tarea habitual es determinar en qué nodo se hizo clic y responder de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="eca2e-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="eca2e-104">Para determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="eca2e-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="eca2e-105">Use el <xref:System.EventArgs> objeto para devolver una referencia al objeto de nodo en el que se ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="eca2e-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="eca2e-106">Determine en qué nodo se hizo clic comprobando la <xref:System.Windows.Forms.TreeViewEventArgs> clase, que contiene los datos relacionados con el evento.</span><span class="sxs-lookup"><span data-stu-id="eca2e-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="eca2e-107">Como alternativa, puede <xref:System.Windows.Forms.MouseEventArgs> utilizar el <xref:System.Windows.Forms.Control.MouseDown> del evento o <xref:System.Drawing.Point.Y%2A> <xref:System.Windows.Forms.Control.MouseUp> paraobtener<xref:System.Drawing.Point.X%2A> los valores de coordenada y de dondeseprodujoelclic.<xref:System.Drawing.Point></span><span class="sxs-lookup"><span data-stu-id="eca2e-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="eca2e-108">A continuación, use <xref:System.Windows.Forms.TreeView> el método <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> del control para determinar en qué nodo se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="eca2e-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca2e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="eca2e-109">See also</span></span>

- [<span data-ttu-id="eca2e-110">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="eca2e-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
