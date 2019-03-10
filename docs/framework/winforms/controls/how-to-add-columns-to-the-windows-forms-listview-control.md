---
title: Procedimiento Agregar columnas al Control de ListView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 4937c31da5dd54cb96090c573e7bdba7a0c7d834
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718966"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Filtrar Agregar columnas al Control de ListView de Windows Forms
En la vista de detalles, el <xref:System.Windows.Forms.ListView> control puede mostrar varias columnas para cada elemento de lista. Puede usar las columnas para mostrar al usuario a varios tipos de información sobre cada elemento de lista. Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, tipo de archivo, tamaño y fecha de que última modificación del archivo. Para obtener información acerca de cómo rellenar las columnas después de crearlos, vea [Cómo: Mostrar subelementos en columnas con el Windows Forms Control ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Para agregar columnas mediante programación  
  
1.  Establecer el control <xref:System.Windows.Forms.ListView.View%2A> propiedad <xref:System.Windows.Forms.View.Details>.  
  
2.  Use la <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> método de la vista de lista <xref:System.Windows.Forms.ListView.Columns%2A> propiedad.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListView>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
