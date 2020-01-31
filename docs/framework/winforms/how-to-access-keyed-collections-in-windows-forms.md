---
title: 'Cómo: obtener acceso a colecciones con clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739615"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Cómo: Obtener acceso a colecciones con claves en Windows Forms

- Puede tener acceso a elementos individuales de la colección por clave. Esta funcionalidad se ha agregado a muchas clases de colección que suelen usar Windows Forms aplicaciones. En la lista siguiente se muestran algunas de las clases de colección que tienen colecciones con clave accesibles:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 La clave asociada con un elemento de una colección es normalmente el nombre del elemento. Los procedimientos siguientes muestran cómo usar las clases de colección para realizar tareas comunes.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Para buscar y dar el foco a un control anidado en una colección de controles  
  
- Utilice los métodos <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> y <xref:System.Windows.Forms.Control.Focus%2A> para especificar el nombre del control que se va a buscar y proporcionar el foco.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Para tener acceso a una imagen en una colección de imágenes  
  
- Use la propiedad <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> para especificar el nombre de la imagen a la que desea obtener acceso.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Para establecer una página de ficha como la pestaña seleccionada  
  
- Use la propiedad <xref:System.Windows.Forms.TabControl.SelectedTab%2A> junto con la propiedad <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> para especificar el nombre de la página de ficha que se va a establecer como la pestaña seleccionada.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a los formularios Windows Forms](getting-started-with-windows-forms.md)
- [Agregar o quitar imágenes con el componente ImageList de Windows Forms](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
