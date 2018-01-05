---
title: "Cómo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92037be2280eaa248951ff9bad82b7a1581a4fd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Cómo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath
Este ejemplo muestra cómo enlazar a [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] datos mediante una <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con un <xref:System.Windows.Data.XmlDataProvider>, los datos que se pueden tener acceso a través del enlace de datos en la aplicación subyacentes pueden ser cualquier árbol de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodos. En otras palabras, un <xref:System.Windows.Data.XmlDataProvider> proporciona una manera cómoda de usar cualquier árbol de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] nodos como un origen de enlace.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los datos se incrustan directamente como un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *isla de datos* dentro de la <xref:System.Windows.FrameworkElement.Resources%2A> sección. Una isla de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] se debe encapsular entre etiquetas `<x:XData>` y tener siempre un nodo raíz único, que se corresponde con *Inventory* en este ejemplo.  
  
> [!NOTE]
>  El nodo raíz de los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tiene un atributo **xmlns** que establece el espacio de nombres de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en una cadena vacía. Se trata de un requisito para aplicar las consultas XPath a una isla de datos insertada dentro de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En este caso en línea, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], y, por tanto, la isla de datos, hereda la <xref:System.Windows> espacio de nombres. Por este motivo, debe establecer el espacio de nombres en blanco para impedir que las consultas XPath que se está calificada por el <xref:System.Windows> espacio de nombres, que podría suministrar las consultas.  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Como se muestra en este ejemplo, para crear la misma declaración de enlace en la sintaxis de atributo es preciso crear caracteres de escape correctos para los caracteres especiales. Para más información, consulte [XML Character Entities and XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md) (Entidades de caracteres XML y XAML).  
  
 El <xref:System.Windows.Controls.ListBox> mostrará los siguientes elementos cuando se ejecuta este ejemplo. Se trata de los elementos *Title* de todos los elementos que se encuentran bajo *Books* cuyo valor de *Stock* sea "*out*" o cuyo valor de *Number* sea 3 o mayor o igual que 8. Tenga en cuenta que ninguna *CD* se devuelven los elementos porque el <xref:System.Windows.Data.XmlDataProvider.XPath%2A> valor establecido en el <xref:System.Windows.Data.XmlDataProvider> indica que solo el *libros* elementos se deberían exponer (básicamente, estableciendo un filtro).  
  
 ![Ejemplo de XPath](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 En este ejemplo, se muestran los títulos de libros porque la <xref:System.Windows.Data.Binding.XPath%2A> de la <xref:System.Windows.Controls.TextBlock> enlace en el <xref:System.Windows.DataTemplate> se establece en "*título*". Si desea mostrar el valor de un atributo, como el *ISBN*, establecería que <xref:System.Windows.Data.Binding.XPath%2A> valor a "`@ISBN`".  
  
 El método XmlNode.SelectNodes administra las propiedades **XPath** en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Puede modificar las consultas **XPath** para obtener resultados distintos. Estos son algunos ejemplos para la <xref:System.Windows.Data.Binding.XPath%2A> consultar en el límite <xref:System.Windows.Controls.ListBox> del ejemplo anterior:  
  
-   `XPath="Book[1]"` devolverá el primer elemento de libro ("XML in Action"). Tenga en cuenta que los índices de **XPath** se basan en 1, no en 0.  
  
-   `XPath="Book[@*]"` devolverá todos los elementos con cualquier atributo.  
  
-   `XPath="Book[last()-1]"` devolverá los elementos de libro del segundo al último ("Introducing Microsoft .NET").  
  
-   `XPath="*[position()>3]"` devolverá todos los elementos de libro excepto los 3 primeros.  
  
 Al ejecutar un **XPath** de consulta, devuelve un <xref:System.Xml.XmlNode> o una lista de XmlNodes. <xref:System.Xml.XmlNode>es un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objeto, lo que significa que puede usar el <xref:System.Windows.Data.Binding.Path%2A> propiedad que se va a enlazar a la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] propiedades. Remítase de nuevo al ejemplo anterior. Si el resto del ejemplo permanece igual y cambia el <xref:System.Windows.Controls.TextBlock> enlace al siguiente, verá los nombres de los objetos XmlNodes devueltos en el <xref:System.Windows.Controls.ListBox>. En este caso, el nombre de todos los nodos devueltos es "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 En algunas aplicaciones, puede que no sea conveniente incrustar [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] como una isla de datos dentro del código fuente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ya que es imprescindible conocer el contenido exacto de los datos en tiempo de compilación. Por lo tanto, también se admite la obtención de los datos de un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] externo, como en el ejemplo siguiente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Si el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos residen en un equipo remoto [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] archivo, tendría que definir acceso a los datos mediante la asignación de una adecuada [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] a la <xref:System.Windows.Data.XmlDataProvider.Source%2A> atributo como se indica a continuación:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [Enlazar a los resultados de una consulta LINQ to XML, XDocument o XElement](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [Usar el patrón principal-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
