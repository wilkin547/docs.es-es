---
title: "C&#243;mo: Usar el patr&#243;n principal-detalle con datos XML jer&#225;rquicos | Microsoft Docs"
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
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Usar el patr&#243;n principal-detalle con datos XML jer&#225;rquicos
En este ejemplo se muestra cómo implementar el patrón principal\-detalle con datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] jerárquicos.  
  
## Ejemplo  
 Este ejemplo es la versión de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] del ejemplo descrito en [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  En este ejemplo, los datos pertenecen al archivo `League.xml`.  Observe que el tercer control <xref:System.Windows.Controls.ListBox> realiza el seguimiento de los cambios de selección del segundo <xref:System.Windows.Controls.ListBox> enlazándose a su propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.  
  
 [!code-xml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## Vea también  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)