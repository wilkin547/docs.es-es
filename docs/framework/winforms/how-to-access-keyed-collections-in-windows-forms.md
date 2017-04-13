---
title: "How to: Access Keyed Collections in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "keyed collections [Windows Forms]"
  - "collections, accessing with keys"
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Access Keyed Collections in Windows Forms
-   Se puede tener acceso a elementos de colección individuales por clave.  Esta funcionalidad se ha agregado a muchas clases de colección que suelen utilizar las aplicaciones de Windows Forms.  En la lista siguiente se muestran algunas de las clases de colección que tienen colecciones con claves a las que se puede tener acceso:  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 La clave asociada a un elemento de una colección es normalmente el nombre del elemento.  Los procedimientos siguientes muestran cómo utilizar clases de colección para realizar tareas comunes.  
  
### Para buscar un control anidado en una colección de controles y asignarle el foco  
  
-   Utilice los métodos <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> y <xref:System.Windows.Forms.Control.Focus%2A> para especificar el nombre del control que desea encontrar y al que desea asignar el foco.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### Para tener acceso a una imagen en una colección de imágenes  
  
-   Utilice la propiedad <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> para especificar el nombre de la imagen a la que desea obtener acceso.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### Para establecer una página de fichas como la ficha seleccionada  
  
-   Utilice la propiedad <xref:System.Windows.Forms.TabControl.SelectedTab%2A> junto con la propiedad <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> para especificar el nombre de la página de fichas que desea establecer como la ficha seleccionada.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## Vea también  
 [Getting Started with Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)   
 [Cómo: Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)