---
title: Agrupar elementos en el control ListView
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736629"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Cómo: Agrupar elementos en un control ListView de Windows Forms
Con la característica de agrupación del control <xref:System.Windows.Forms.ListView>, puede mostrar conjuntos de elementos relacionados en grupos. Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación alfabética de elementos, por fecha o cualquier otra agrupación lógica. En la imagen siguiente se muestran algunos elementos agrupados.  
  
 ![Captura de pantalla de grupos de ListView pares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 Para habilitar la agrupación, primero debe crear uno o más grupos en el diseñador o mediante programación. Una vez definido un grupo, puede asignar elementos de <xref:System.Windows.Forms.ListView> a grupos. También puede trasladar elementos de un grupo a otro mediante programación.  
  
### <a name="to-add-groups"></a>Para agregar grupos  
  
1. Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Para quitar grupos  
  
1. Use el método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> de la colección de <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     El método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> quita un solo grupo; el método <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> quita todos los grupos de la lista.  
  
    > [!NOTE]
    > Al quitar un grupo no se quitan los elementos de ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Para asignar elementos a grupos o para trasladar elementos entre grupos  
  
1. Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> de elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView (control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
