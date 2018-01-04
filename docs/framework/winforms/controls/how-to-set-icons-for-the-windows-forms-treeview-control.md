---
title: "Cómo: Establecer iconos del control TreeView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d6133a378c4939a20cef6bab8f3ee5f36b9c3cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Cómo: Establecer iconos del control TreeView de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.TreeView> control puede mostrar iconos junto a cada nodo. Los iconos se sitúan inmediatamente a la izquierda del texto del nodo. Para mostrar estos iconos, deberá asociar la vista de árbol con un <xref:System.Windows.Forms.ImageList> control. Para obtener más información acerca de las listas de imágenes, vea [ImageList (componente)](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Un error en la versión 1.1 de Microsoft .NET Framework evita que las imágenes que aparecen en <xref:System.Windows.Forms.TreeView> nodos cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Para solucionar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en su `Main` método inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Este error se ha corregido en [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Para mostrar imágenes en una vista de árbol  
  
1.  Establecer el <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.ImageList%2A> propiedad existente <xref:System.Windows.Forms.ImageList> control que se va a usar.  
  
     Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en el código.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Establecer el nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedades. El <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> propiedad determina la imagen que se muestra para los Estados del nodo normal y expandido y el <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedad determina la imagen mostrada para el estado del nodo seleccionado.  
  
     Estas propiedades pueden establecerse en código o dentro del Editor TreeNode. Para abrir el Editor TreeNode, haga clic en el botón de puntos suspensivos ( ![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad en la ventana Propiedades.  
  
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
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
