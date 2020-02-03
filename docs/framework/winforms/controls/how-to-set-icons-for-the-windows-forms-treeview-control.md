---
title: Establecer iconos para el control TreeView
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
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737265"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Cómo: Establecer iconos del control TreeView de Windows Forms
El control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar iconos junto a cada nodo. Los iconos se colocan a la izquierda inmediata del texto del nodo. Para mostrar estos iconos, debe asociar la vista de árbol a un control de <xref:System.Windows.Forms.ImageList>. Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
> Un error en Microsoft .NET Framework versión 1,1 impide que las imágenes aparezcan en <xref:System.Windows.Forms.TreeView> nodos cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en el método `Main` inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Este error se corrigió en .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Para mostrar imágenes en una vista de árbol  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> del control <xref:System.Windows.Forms.TreeView> en el control de <xref:System.Windows.Forms.ImageList> existente que desee usar.  
  
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
  
2. Establezca las propiedades <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo. La propiedad <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> determina la imagen que se muestra para los Estados normal y expandido del nodo, y la propiedad <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> determina la imagen que se muestra para el estado seleccionado del nodo.  
  
     Estas propiedades se pueden establecer en el código o en el editor TreeNode. Para abrir el editor TreeNode, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> en la ventana Propiedades.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Agregar y quitar nodos con el control TreeView de formularios Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
