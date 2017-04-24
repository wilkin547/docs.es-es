---
title: "C&#243;mo: Usar espacios de nombres XML en el enlace de datos | Microsoft Docs"
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
  - "enlace de datos, espacios de nombres XML"
  - "espacios de nombres, XML"
  - "XML, espacios de nombres"
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Usar espacios de nombres XML en el enlace de datos
## Ejemplo  
 En este ejemplo se muestra cómo administrar los espacios de nombres especificados en el [origen de enlace](GTMT) de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Puede utilizar el elemento <xref:System.Windows.Data.XmlNamespaceMapping> para asignar el espacio de nombres a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente.  A continuación, puede utilizar <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia al espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  En este ejemplo, <xref:System.Windows.Controls.ListBox> muestra los elementos *title* y *dc:date* de cada *item*.  
  
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/xaml/VS_Snippets_Wpf/XmlnsBind/XAML/Window1.xaml#xmlnamespacemapping)]  -->
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBind/CS/Window1.xaml#xmlnamespacemapping)]  -->  
  
 Observe que la propiedad <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> que se especifica no tiene que coincidir necesariamente con la utilizada en el origen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; aunque el prefijo cambie en el origen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], la asignación sigue funcionando.  
  
 En este ejemplo concreto, los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] proceden de un servicio Web, pero el elemento <xref:System.Windows.Data.XmlNamespaceMapping> también funciona con datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] insertados o datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de un archivo incrustado.  
  
## Vea también  
 [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)