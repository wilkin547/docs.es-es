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
ms.openlocfilehash: 7a0e2b69bbec0eb03d40bee2c8e2d4bc9c3558f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742011"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="6f642-102">Cómo: Determinar en qué nodo de TreeView se hizo clic (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6f642-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="6f642-103">Al trabajar con el control de <xref:System.Windows.Forms.TreeView> de Windows Forms, una tarea habitual es determinar en qué nodo se hizo clic y responder de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="6f642-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="6f642-104">Para determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="6f642-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="6f642-105">Utilice el objeto <xref:System.EventArgs> para devolver una referencia al objeto de nodo en el que se ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="6f642-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="6f642-106">Determine en qué nodo se hizo clic comprobando la clase <xref:System.Windows.Forms.TreeViewEventArgs>, que contiene los datos relacionados con el evento.</span><span class="sxs-lookup"><span data-stu-id="6f642-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="6f642-107">Como alternativa, puede usar el <xref:System.Windows.Forms.MouseEventArgs> del evento <xref:System.Windows.Forms.Control.MouseDown> o <xref:System.Windows.Forms.Control.MouseUp> para obtener los valores de las coordenadas <xref:System.Drawing.Point.X%2A> y <xref:System.Drawing.Point.Y%2A> de la <xref:System.Drawing.Point> en la que se ha producido el clic.</span><span class="sxs-lookup"><span data-stu-id="6f642-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="6f642-108">A continuación, use el método <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> del control <xref:System.Windows.Forms.TreeView> para determinar en qué nodo se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="6f642-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f642-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f642-109">See also</span></span>

- [<span data-ttu-id="6f642-110">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="6f642-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
