---
title: Agregar columnas al control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744581"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Cómo: Agregar columnas al control ListView de Windows Forms
En la vista de detalles, el control <xref:System.Windows.Forms.ListView> puede mostrar varias columnas para cada elemento de la lista. Puede usar las columnas para mostrar al usuario varios tipos de información sobre cada elemento de la lista. Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez. Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Para agregar columnas mediante programación  
  
1. Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> del control en <xref:System.Windows.Forms.View.Details>.  
  
2. Use el método <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ListView.Columns%2A> de la vista de lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- [ListView (control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
