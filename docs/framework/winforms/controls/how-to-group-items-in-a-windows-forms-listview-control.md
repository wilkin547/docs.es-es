---
title: Procedimiento Agrupar elementos en un Control ListView de formularios de Windows
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
ms.openlocfilehash: a14d4560a229e62bc0759b6b4eab8087eb53f030
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722963"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Filtrar Agrupar elementos en un Control ListView de formularios de Windows
Con la característica de agrupación de la <xref:System.Windows.Forms.ListView> control, puede mostrar conjuntos relacionados de elementos en grupos. Estos grupos se separan en la pantalla con los encabezados de grupo horizontal que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación sea más fácil de listas grandes mediante la agrupación de elementos por orden alfabético, por fecha, o por cualquier otra agrupación lógica. La imagen siguiente muestra algunos elementos agrupados.  
  
 ![Grupos ListView](./media/listviewgroups.gif "ListViewGroups")  
Elementos de ListView agrupados  
  
 Para habilitar la agrupación, primero debe crear uno o más grupos en el diseñador o mediante programación. Una vez definido un grupo, puede asignar <xref:System.Windows.Forms.ListView> elementos a grupos. Puede también mover elementos de un grupo a otro mediante programación.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> grupos solo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama el <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método. En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y no aparecerán los grupos. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Para agregar grupos  
  
1.  Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Para quitar grupos  
  
1.  Use la <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Groups%2A> colección.  
  
     El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un grupo único; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.  
  
    > [!NOTE]
    >  Quitar un grupo no quita los elementos dentro de ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Para asignar elementos a grupos o mover elementos entre grupos  
  
1.  Establecer el <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> propiedad de los elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
