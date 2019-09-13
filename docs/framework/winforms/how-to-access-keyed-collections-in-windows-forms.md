---
title: Procedimiento para obtener acceso a colecciones con claves en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928527"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Procedimiento para obtener acceso a colecciones con claves en formularios Windows Forms

- Puede tener acceso a elementos individuales de la colección por clave. Esta funcionalidad se ha agregado a muchas clases de colección que suelen usar Windows Forms aplicaciones. En la lista siguiente se muestran algunas de las clases de colección que tienen colecciones con clave accesibles:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 La clave asociada con un elemento de una colección es normalmente el nombre del elemento. Los procedimientos siguientes muestran cómo usar las clases de colección para realizar tareas comunes.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Para buscar y dar el foco a un control anidado en una colección de controles  
  
- Utilice los <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> métodos <xref:System.Windows.Forms.Control.Focus%2A> y para especificar el nombre del control que se va a buscar y proporcionar el foco.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Para tener acceso a una imagen en una colección de imágenes  
  
- Utilice la <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> propiedad para especificar el nombre de la imagen a la que desea obtener acceso.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Para establecer una página de ficha como la pestaña seleccionada  
  
- Utilice la <xref:System.Windows.Forms.TabControl.SelectedTab%2A> propiedad junto con la <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> propiedad para especificar el nombre de la página de ficha que se va a establecer como la pestaña seleccionada.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a los formularios Windows Forms](getting-started-with-windows-forms.md)
- [Cómo: Agregar o quitar imágenes con el componente de ImageList Windows Forms](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
