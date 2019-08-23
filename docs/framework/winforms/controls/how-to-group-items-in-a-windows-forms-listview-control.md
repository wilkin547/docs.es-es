---
title: Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms
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
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966630"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms
Con la característica de agrupación del <xref:System.Windows.Forms.ListView> control, puede mostrar conjuntos relacionados de elementos en grupos. Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación de elementos por orden alfabético, por fecha o por cualquier otra agrupación lógica. En la imagen siguiente se muestran algunos elementos agrupados.  
  
 ![Captura de pantalla de grupos de ListView pares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 Para habilitar la agrupación, primero debe crear uno o más grupos en el diseñador o mediante programación. Una vez definido un grupo, puede asignar <xref:System.Windows.Forms.ListView> elementos a los grupos. También puede trasladar elementos de un grupo a otro mediante programación.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ListView>los grupos solo están disponibles [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] en cuando la aplicación <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> llama al método. En los sistemas operativos anteriores, cualquier código relacionado con los grupos no tiene ningún efecto y los grupos no aparecerán. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Para agregar grupos  
  
1. Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Para quitar grupos  
  
1. Use el <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> o de la <xref:System.Windows.Forms.ListView.Groups%2A> colección.  
  
     El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un solo grupo; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.  
  
    > [!NOTE]
    > Al quitar un grupo no se quitan los elementos de ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Para asignar elementos a grupos o para trasladar elementos entre grupos  
  
1. Establezca la <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> propiedad de elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
