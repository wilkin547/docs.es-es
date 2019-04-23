---
title: Procedimiento para mostrar subelementos en columnas con el control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 318521cc1377be89ef54706d80c8b2990a6ba1b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339299"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Procedimiento para mostrar subelementos en columnas con el control ListView de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.ListView> control puede mostrar texto adicional o subelementos, para cada elemento de la vista de detalles. La primera columna muestra el texto del elemento, por ejemplo un número de empleado. La segunda, terceros y posteriores columnas muestran el primero, segundo y siguientes subelementos asociados.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Para agregar subelementos a un elemento de lista  
  
1. Agregue las columnas necesarias. Dado que la primera columna muestra el elemento <xref:System.Windows.Forms.ListView.Text%2A> propiedad, se necesita una columna más que el número de subelementos. Para obtener más información sobre cómo agregar columnas, vea [Cómo: Agregar columnas a la Windows Forms Control ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2. Llame a la <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.ListViewItem.SubItems%2A> propiedad de un elemento. El ejemplo de código siguiente establece el nombre del empleado y el departamento de un elemento de lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Cómo: Agregar columnas al Control de ListView de Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Cómo: Mostrar iconos para el Control ListView de formularios de Windows](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
