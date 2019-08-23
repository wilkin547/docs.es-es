---
title: Procedimiento para establecer iconos del control TreeView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909812"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Procedimiento para establecer iconos del control TreeView de formularios Windows Forms
El control <xref:System.Windows.Forms.TreeView> Windows Forms puede mostrar iconos junto a cada nodo. Los iconos se colocan a la izquierda inmediata del texto del nodo. Para mostrar estos iconos, debe asociar la vista de árbol a <xref:System.Windows.Forms.ImageList> un control. Para obtener más información acerca de las listas de imágenes, consulte el [ [componente ImageList](imagelist-component-windows-forms.md) y cómo: Agregue o quite imágenes con el componente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)ImageList de Windows Forms.  
  
> [!NOTE]
> Un error en la versión 1,1 de Microsoft .NET Framework impide que las imágenes <xref:System.Windows.Forms.TreeView> aparezcan en los nodos <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>cuando la aplicación llama a. Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en el `Main` método inmediatamente después de <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>llamar a. Este error se corrigió en .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Para mostrar imágenes en una vista de árbol  
  
1. Establezca la <xref:System.Windows.Forms.TreeView> propiedad del <xref:System.Windows.Forms.TreeView.ImageList%2A> control en el control <xref:System.Windows.Forms.ImageList> existente que desee usar.  
  
     Estas propiedades se pueden establecer en el diseñador con el ventana Propiedades o en el código.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Establezca las propiedades y <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo. La <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> propiedad determina la imagen que se muestra para los Estados normal y expandido del nodo <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> , y la propiedad determina la imagen que se muestra para el estado seleccionado del nodo.  
  
     Estas propiedades se pueden establecer en el código o en el editor TreeNode. Para abrir el editor TreeNode, haga clic en el botón ![de puntos suspensivos (el botón de puntos suspensivos (...) en](./media/visual-studio-ellipsis-button.png)el ventana Propiedades de Visual <xref:System.Windows.Forms.TreeView.Nodes%2A> Studio.) junto a la propiedad en el ventana Propiedades.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>Vea también

- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Procedimientos: Agregar y quitar nodos con el control TreeView Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedimientos: Recorrer en iteración todos los nodos de un control TreeView Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a un control TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
