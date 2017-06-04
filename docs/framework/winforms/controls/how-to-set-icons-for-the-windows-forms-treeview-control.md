---
title: "C&#243;mo: Establecer iconos del control TreeView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], TreeView (control)"
  - "iconos, establecer para el control TreeView"
  - "ImageList (componente) [Windows Forms], agregar imágenes"
  - "nodos de árbol en el control TreeView, iconos"
  - "TreeView (control) [Windows Forms], iconos de nodo"
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Establecer iconos del control TreeView de formularios Windows Forms
El control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms puede mostrar iconos junto a cada nodo.  Los iconos se sitúan inmediatamente a la izquierda del texto del nodo.  Para mostrar estos iconos, deberá asociar la vista de árbol con un control <xref:System.Windows.Forms.ImageList>.  Para obtener más información sobre las listas de imágenes, vea [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Un error en la versión 1.1 de Microsoft .NET Framework evita que las imágenes aparezcan en los nodos <xref:System.Windows.Forms.TreeView> cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> en su método `Main` inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  Este error se corrige en [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### Para mostrar imágenes en una vista de árbol  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> del control <xref:System.Windows.Forms.TreeView> en el control <xref:System.Windows.Forms.ImageList> existente que desee utilizar.  
  
     Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en código.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Establezca las propiedades <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo.  La propiedad <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> determina la imagen que se muestra para los estados normal y expandido del nodo, y la propiedad <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> determina la imagen que se muestra para el estado seleccionado del nodo.  
  
     Estas propiedades pueden establecerse en código o dentro del Editor TreeNode.  Para abrir el Editor TreeNode, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> en la ventana Propiedades.  
  
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
  
## Vea también  
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Cómo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Cómo: Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Cómo: Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)