---
title: "C&#243;mo: Hacer que los datos est&#233;n disponibles para el enlace en XAML | Microsoft Docs"
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
  - "enlazar datos, poner los datos a disposición de"
  - "enlace de datos, hacer que los datos estén disponibles para el enlace"
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Hacer que los datos est&#233;n disponibles para el enlace en XAML
En este tema se explican maneras diferentes de hacer que los datos estén disponibles para el enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], dependiendo de las necesidades de la aplicación.  
  
## Ejemplo  
 Si tiene un objeto [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] al que desea enlazar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una manera de hacer que esté disponible para el enlace es definirlo como recurso y asignarle una clave `x:Key`.  En el ejemplo siguiente, tenemos un objeto `Person` con una propiedad de cadena denominada `PersonName`.  El objeto `Person` se define en el espacio de nombres denominado `SDKSample`.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 A continuación, puede enlazar al objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como se muestra en el ejemplo siguiente.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Como alternativa, puede utilizar la clase <xref:System.Windows.Data.ObjectDataProvider>, como en el ejemplo siguiente.  
  
 [!code-xml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 El enlace se define de la misma manera:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 En este ejemplo concreto, el resultado es el mismo: dispone de <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe`.  Sin embargo, la clase <xref:System.Windows.Data.ObjectDataProvider> proporciona funcionalidad que permite enlazar al resultado de un método.  Puede optar por utilizar la clase <xref:System.Windows.Data.ObjectDataProvider> si necesita la funcionalidad que proporciona.  
  
 Sin embargo, si el enlace se va a establecer a un objeto que ya se ha creado, deberá establecer `DataContext` mediante código, como en el ejemplo siguiente.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Para tener acceso a los datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el enlace a través de la clase <xref:System.Windows.Data.XmlDataProvider>, vea [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  Para tener acceso a los datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el enlace a través de la clase <xref:System.Windows.Data.ObjectDataProvider>, vea [Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Para obtener información sobre las distintas maneras de especificar los datos a los que se establece el enlace, consulte [Especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  Para obtener información sobre qué tipos de datos se pueden enlazar o sobre cómo implementar sus propios objetos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] para el enlace, consulte [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)