---
title: Mostrar subelementos en columnas con el control ListView
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
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745546"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms
El control Windows Forms <xref:System.Windows.Forms.ListView> puede mostrar texto adicional, o subelementos, para cada elemento en la vista de detalles. La primera columna muestra el texto del elemento, por ejemplo un número de empleado. Las columnas segunda, tercera y subsiguientes muestran el primer, segundo y subelementos asociados posteriores.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Para agregar subelementos a un elemento de lista  
  
1. Agregue las columnas necesarias. Dado que la primera columna mostrará la propiedad <xref:System.Windows.Forms.ListView.Text%2A> del elemento, se necesita una columna más que los subelementos. Para obtener más información sobre cómo agregar columnas, vea [Cómo: Agregar columnas al control ListView de Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2. Llame al método <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> de la colección devuelta por la propiedad <xref:System.Windows.Forms.ListViewItem.SubItems%2A> de un elemento. En el ejemplo de código siguiente se establece el nombre del empleado y el Departamento para un elemento de lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Consulte también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Agregar columnas al control ListView de formularios Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
