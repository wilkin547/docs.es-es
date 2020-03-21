---
title: Agrupar elementos en ListView Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141996"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Cómo: Agrupar elementos en un control ListView de formularios Windows Forms
Con la característica <xref:System.Windows.Forms.ListView> de agrupación del control, puede mostrar conjuntos de elementos relacionados en grupos. Estos grupos están separados en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo. Puede utilizar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes agrupando elementos alfabéticamente, por fecha o por cualquier otra agrupación lógica. La siguiente imagen muestra algunos elementos agrupados.  
  
 ![Captura de pantalla de grupos ListView impares e pares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 Para habilitar la agrupación, primero debe crear uno o varios grupos en el diseñador o mediante programación. Una vez definido un grupo, <xref:System.Windows.Forms.ListView> puede asignar artículos a grupos. También puede mover elementos de un grupo a otro mediante programación.  
  
### <a name="to-add-groups"></a>Para añadir grupos  
  
1. Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Para eliminar grupos  
  
1. Utilice <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método <xref:System.Windows.Forms.ListView.Groups%2A> o de la colección.  
  
     El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un solo grupo; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.  
  
    > [!NOTE]
    > La eliminación de un grupo no quita los elementos de ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Para asignar artículos a grupos o mover elementos entre grupos  
  
1. Establezca <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> la propiedad de elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [Control ListView](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
