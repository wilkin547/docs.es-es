---
title: "C&#243;mo: Agrupar elementos en un control ListView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "agrupar"
  - "grupos"
  - "grupos, de controles de Windows Forms"
  - "vistas de lista, agrupar elementos"
  - "listas, agrupar elementos"
  - "ListView (control) [Windows Forms], agrupar elementos"
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Agrupar elementos en un control ListView de formularios Windows Forms
Con la característica de agrupación del control <xref:System.Windows.Forms.ListView> puede mostrar conjuntos relacionados de elementos en grupos.  Estos grupos se separan en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo.  Puede utilizar grupos de elementos <xref:System.Windows.Forms.ListView> para hacer que la navegación por listas de gran tamaño sea más fácil agrupando alfabéticamente los elementos, por fecha, o por cualquier otra agrupación lógica.  La imagen siguiente muestra algunos elementos agrupados.  
  
 ![Grupos ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
Elementos agrupados ListView  
  
 Para habilitar la agrupación, en primer lugar se debe crear uno o más grupos, ya sea en el diseñador o mediante programación.  Una vez definido un grupo, puede asignar elementos <xref:System.Windows.Forms.ListView> a los grupos.  También puede mover elementos de un grupo a otro mediante programación.  
  
> [!NOTE]
>  Los grupos <xref:System.Windows.Forms.ListView> sólo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y no aparecerán los grupos.  Para obtener más información, vea <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
  
### Para agregar grupos  
  
1.  Utilice el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### Para quitar grupos  
  
1.  Utilice el método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     El método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> quita un solo grupo; el método <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> quita todos los grupos de la lista.  
  
    > [!NOTE]
    >  Cuando se quita un grupo no se quitan los elementos contenidos en ese grupo.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### Para asignar elementos a grupos o mover elementos entre grupos  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=fullName> de elementos individuales.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Características de Windows XP y controles de formularios Windows Forms](http://msdn.microsoft.com/es-es/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)