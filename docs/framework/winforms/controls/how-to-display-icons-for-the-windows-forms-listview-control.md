---
title: Mostrar iconos para el control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744506"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Cómo: Mostrar iconos del control ListView de Windows Forms
El control <xref:System.Windows.Forms.ListView> de Windows Forms puede mostrar iconos de tres listas de imágenes. Las vistas List, details y SmallIcon muestran imágenes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A>. La vista LargeIcon muestra imágenes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.LargeImageList%2A>. Una vista de lista también puede mostrar un conjunto adicional de iconos, establecido en la propiedad <xref:System.Windows.Forms.ListView.StateImageList%2A>, junto a los iconos grandes o pequeños. Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Para mostrar imágenes en una vista de lista  
  
1. Establezca la propiedad adecuada (<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>o <xref:System.Windows.Forms.ListView.StateImageList%2A>) en el componente de <xref:System.Windows.Forms.ImageList> existente que desea usar.  
  
     Estas propiedades se pueden establecer en el diseñador con el ventana Propiedades o en el código.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> para cada elemento de lista que tenga un icono asociado.  
  
     Estas propiedades se pueden establecer en el código o en el **Editor de la colección ListViewItem**. Para abrir el **Editor de la colección ListViewItem**, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A> en la ventana **propiedades** .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Agregar columnas al control ListView de formularios Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList (componente)](imagelist-component-windows-forms.md)
