---
title: "C&#243;mo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath | Microsoft Docs"
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
  - "enlace, a datos XML mediante consultas XMLDataProvider"
  - "enlace de datos, enlazar a datos XML mediante consultas XMLDataProvider"
  - "XmlDataProvider, enlazar a datos XML"
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath
En este ejemplo se muestra cómo enlazar a datos [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] utilizando <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con <xref:System.Windows.Data.XmlDataProvider>, los datos subyacentes a los que se puede tener acceso mediante el enlace de datos en la aplicación pueden ser cualquier árbol de nodos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  En otras palabras, <xref:System.Windows.Data.XmlDataProvider> proporciona una manera cómoda de utilizar cualquier árbol de nodos [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] como [origen de enlace](GTMT).  
  
## Ejemplo  
 En el ejemplo siguiente, los datos se incrustan directamente como una *isla de datos* de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en la sección <xref:System.Windows.FrameworkElement.Resources%2A>.  Una isla de datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] se debe incluir en etiquetas `<x:XData>` y tener siempre un nodo raíz único, que es *Inventory* en este ejemplo.  
  
> [!NOTE]
>  El nodo raíz de los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tiene un atributo **xmlns** que establece el espacio de nombres de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en una cadena vacía.  Se trata de un requisito para aplicar las consultas XPath a una isla de datos insertada dentro de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  En este caso de inserción, el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y, en consecuencia, la isla de datos, hereda el espacio de nombres <xref:System.Windows>.  Por ello, es preciso establecer el espacio de nombres en blanco, a fin de evitar que el espacio de nombres <xref:System.Windows> certifique las consultas Xpath, lo que las dirigiría incorrectamente.  
  
 [!code-xml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Como se muestra en este ejemplo, para crear la misma declaración de enlace en la sintaxis de atributo es preciso crear caracteres de escape correctos para los caracteres especiales.  Para obtener más información, vea [Entidades de caracteres XML y XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 <xref:System.Windows.Controls.ListBox> mostrará los elementos siguientes cuando se ejecute este ejemplo.  Se trata de los elementos *Title* de todos los elementos que se encuentran bajo *Books* cuyo valor de *Stock* sea "*out*" o cuyo valor de *Number* sea 3 o mayor o igual que 8.  Observe que no se devuelve ningún elemento *CD* porque el valor de <xref:System.Windows.Data.XmlDataProvider.XPath%2A> establecido en <xref:System.Windows.Data.XmlDataProvider> indica que únicamente se deben exponer los elementos *Books* \(básicamente, estableciendo un filtro\).  
  
 ![Ejemplo de XPath](../../../../docs/framework/wpf/data/media/xpathexample.png "XPathExample")  
  
 En este ejemplo, se muestran los títulos de los libros porque la propiedad <xref:System.Windows.Data.Binding.XPath%2A> del enlace del objeto <xref:System.Windows.Controls.TextBlock> en <xref:System.Windows.DataTemplate> se establece en "*Title*".  Si desea mostrar el valor de un atributo, como el *ISBN*, deberá establecer ese valor de <xref:System.Windows.Data.Binding.XPath%2A> en "`@ISBN`".  
  
 El método XmlNode.SelectNodes administra las propiedades **XPath** en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Puede modificar las consultas **del XPath** para obtener resultados diferentes.  A continuación se muestran algunos ejemplos para la consulta <xref:System.Windows.Data.Binding.XPath%2A> en el control <xref:System.Windows.Controls.ListBox> enlazado del ejemplo anterior:  
  
-   `XPath="Book[1]"` devolverá el primer elemento de libro \("XML in Action"\).  Observe que los índices de **XPath** se basan en 1, no en 0.  
  
-   `XPath="Book[@*]"` devolverá todos los elementos de libro con cualquier atributo.  
  
-   `XPath="Book[last()-1]"` devolverá los elementos de libro del segundo a último libro \("Introducing Microsoft .NET"\).  
  
-   `XPath="*[position()>3]"` devolverá todos los elementos de libro salvo los 3 primeros.  
  
 Al ejecutar una consulta **XPath**, devuelve un objeto <xref:System.Xml.XmlNode> o una lista de XmlNodes.  <xref:System.Xml.XmlNode> es un objeto [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], lo que significa que puede utilizar la propiedad <xref:System.Windows.Data.Binding.Path%2A> para enlazar a las propiedades de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  Estudie de nuevo el ejemplo anterior.  Si el resto del ejemplo permanece igual y cambia el enlace de <xref:System.Windows.Controls.TextBlock> por lo siguiente, verá los nombres de los objetos XmlNodes devueltos en el control <xref:System.Windows.Controls.ListBox>.  En este caso, el nombre de todos los nodos devueltos es "*Book*".  
  
 [!code-xml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 En algunas aplicaciones, puede que no sea oportuno incrustar [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] como una isla de datos dentro del código fuente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ya que es imprescindible conocer el contenido exacto de los datos en tiempo de compilación.  Por consiguiente, también se admite la obtención de los datos de un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] externo, como en el ejemplo siguiente:  
  
 [!code-xml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] residen en un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] remoto, el acceso a ellos se define asignando una [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] adecuada al atributo <xref:System.Windows.Data.XmlDataProvider.Source%2A>, como sigue:  
  
```  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## Vea también  
 <xref:System.Windows.Data.ObjectDataProvider>   
 [Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)   
 [Usar el patrón principal\-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)