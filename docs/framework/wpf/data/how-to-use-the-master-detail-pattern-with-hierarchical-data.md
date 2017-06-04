---
title: "C&#243;mo: Usar el patr&#243;n principal-detalle con datos jer&#225;rquicos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlace de datos, paradigma de datos principal-detalle"
  - "paradigma de datos principal-detalle"
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Usar el patr&#243;n principal-detalle con datos jer&#225;rquicos
En este ejemplo se muestra cómo implementar el patrón principal\-detalle con datos jerárquicos.  
  
## Ejemplo  
 En este ejemplo, `LeagueList` es una colección de `Leagues`.  Cada `League` tiene un valor `Name` y una colección de `Divisions` y cada `Division` tiene un nombre y una colección de `Teams`.  Cada `Team` tiene un nombre de equipo.  
  
 [!code-xml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 A continuación, se muestra una captura de pantalla del ejemplo.  El control <xref:System.Windows.Controls.ListBox> `Divisions` realiza automáticamente el seguimiento de las selecciones en el control <xref:System.Windows.Controls.ListBox> `Leagues` y muestra los datos correspondientes.  El control <xref:System.Windows.Controls.ListBox> `Teams` realiza el seguimiento de las selecciones en los otros dos controles <xref:System.Windows.Controls.ListBox>.  
  
 ![Ejemplo Master&#45;detail](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Los dos puntos importantes de este ejemplo son:  
  
1.  Los tres controles <xref:System.Windows.Controls.ListBox> están enlazados al mismo origen.  Debe establecer la propiedad <xref:System.Windows.Data.Binding.Path%2A> del enlace para especificar qué nivel de datos desea que muestre el control <xref:System.Windows.Controls.ListBox>.  
  
2.  Debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` en los controles <xref:System.Windows.Controls.ListBox> de la selección de la que está realizando el seguimiento.  Al establecer esta propiedad se garantiza que el elemento seleccionado se establezca siempre como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.  Como alternativa, si el control <xref:System.Windows.Controls.ListBox> obtiene sus datos de un objeto <xref:System.Windows.Data.CollectionViewSource>, sincronizará automáticamente la selección y la actualización.  
  
 La técnica es ligeramente diferente cuando se utilizan datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Para obtener un ejemplo, vea [Usar el patrón principal\-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## Vea también  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)