---
title: "Cómo: Agrupar elementos en un control ListView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12b7126e03f6a6c8363c69a607f4961f13120ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Cómo: Agrupar elementos en un control ListView de formularios Windows Forms
Con la característica de agrupación de la <xref:System.Windows.Forms.ListView> (control), puede mostrar conjuntos de elementos relacionados en grupos. Estos grupos se separan en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación sea más fácil de listas grandes mediante la agrupación de elementos por orden alfabético, por fecha, o por cualquier otra agrupación lógica. La siguiente imagen muestra algunos elementos agrupados.  
  
 ![Grupos ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
Elementos agrupados ListView  
  
 Para habilitar la agrupación, debe crear primero uno o varios grupos en el diseñador o mediante programación. Una vez definido un grupo, puede asignar <xref:System.Windows.Forms.ListView> elementos a grupos. También puede mover elementos de un grupo a otro mediante programación.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>grupos solo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama el <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método. En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y los grupos no aparecerán. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Para agregar grupos  
  
1.  Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Para quitar grupos  
  
1.  Use la <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Groups%2A> colección.  
  
     El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un grupo único; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.  
  
    > [!NOTE]
    >  Quitar un grupo no quita los elementos dentro de ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Para asignar elementos a grupos o mover elementos entre grupos  
  
1.  Establecer el <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> propiedad de los elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Características de Windows XP y controles de Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
