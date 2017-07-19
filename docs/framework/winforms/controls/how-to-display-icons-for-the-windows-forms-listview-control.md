---
title: "C&#243;mo: Mostrar iconos del control ListView de formularios Windows Forms | Microsoft Docs"
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
  - "iconos, mostrar para controles ListView"
  - "ImageList (componente) [Windows Forms], con el control ListView"
  - "vistas de lista, mostrar iconos"
  - "listas, mostrar iconos"
  - "ListView (control) [Windows Forms], mostrar iconos"
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Mostrar iconos del control ListView de formularios Windows Forms
El control <xref:System.Windows.Forms.ListView> de formularios Windows Forms puede mostrar iconos procedentes de tres listas de imágenes.  Las vistas List, Details y SmallIcon muestran imágenes procedentes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A>.  La vista LargeIcon muestra imágenes procedentes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.LargeImageList%2A>.  Asimismo, una vista de lista puede mostrar un conjunto adicional de iconos, que se establece en la propiedad <xref:System.Windows.Forms.ListView.StateImageList%2A>, junto a los iconos grandes o pequeños.  Para obtener más información sobre las listas de imágenes, vea [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### Para mostrar imágenes en una vista de lista  
  
1.  Establezca la propiedad apropiada \(<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A> o <xref:System.Windows.Forms.ListView.StateImageList%2A>\) en el componente <xref:System.Windows.Forms.ImageList> existente que desee utilizar.  
  
     Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en código.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> para cada elemento de la lista que tenga un icono asociado.  
  
     Estas propiedades pueden establecerse en código o dentro del **Editor de la colección de ListViewItem**.  Para abrir el **Editor de la colección de ListViewItem**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A> en la ventana **Propiedades**.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## Vea también  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)