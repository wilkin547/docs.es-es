---
title: Procedimiento para mostrar iconos del control ListView de formularios Windows Forms
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
ms.openlocfilehash: 8e4ae744eecbe894767114179dd63651828b191b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318616"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Procedimiento para mostrar iconos del control ListView de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.ListView> control puede mostrar iconos de tres listas de imágenes. Las vistas lista, detalles y SmallIcon muestran imágenes de la lista de imágenes especificado en el <xref:System.Windows.Forms.ListView.SmallImageList%2A> propiedad. La vista LargeIcon muestra imágenes de la lista de imágenes especificado en el <xref:System.Windows.Forms.ListView.LargeImageList%2A> propiedad. Una vista de lista también puede mostrar un conjunto adicional de iconos, establecidos el <xref:System.Windows.Forms.ListView.StateImageList%2A> propiedad, junto a los iconos grandes o pequeños. Para obtener más información acerca de las listas de imágenes, consulte [componente ImageList](imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Para mostrar imágenes en una vista de lista  
  
1. Establezca la propiedad adecuada,<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, o <xref:System.Windows.Forms.ListView.StateImageList%2A>: existente <xref:System.Windows.Forms.ImageList> componente que desea usar.  
  
     Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en el código.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Establecer el <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> propiedad para cada elemento de lista que tiene un icono asociado.  
  
     Estas propiedades pueden establecerse en código o dentro del **Editor de la colección ListViewItem**. Para abrir el **Editor de la colección ListViewItem**, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.ListView.Items%2A>propiedad en el **propiedades** ventana.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Cómo: Agregar columnas al Control de ListView de Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList (componente)](imagelist-component-windows-forms.md)
