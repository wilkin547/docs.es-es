---
title: Procedimiento Enlazar a datos XML mediante XMLDataProvider y consultas XPath
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: 4833e024fcd352094a2163f11df8572aa4c241f8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944647"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Procedimiento Enlazar a datos XML mediante XMLDataProvider y consultas XPath
En este ejemplo se muestra cómo enlazar a [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] datos <xref:System.Windows.Data.XmlDataProvider>mediante.  
  
 Con, los datos subyacentes a los que se puede tener acceso a través del enlace de datos de la aplicación [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] pueden ser cualquier árbol de nodos. <xref:System.Windows.Data.XmlDataProvider> En otras palabras, un <xref:System.Windows.Data.XmlDataProvider> proporciona una manera cómoda de usar cualquier árbol de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] nodos como origen de enlace.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los datos se incrustan directamente como [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] una *isla* de datos <xref:System.Windows.FrameworkElement.Resources%2A> dentro de la sección. Una isla de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] se debe encapsular entre etiquetas `<x:XData>` y tener siempre un nodo raíz único, que se corresponde con *Inventory* en este ejemplo.  
  
> [!NOTE]
> El nodo raíz de los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tiene un atributo **xmlns** que establece el espacio de nombres de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en una cadena vacía. Se trata de un requisito para aplicar las consultas XPath a una isla de datos insertada dentro de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En este caso en línea, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]y, por tanto, la isla de datos, hereda el espacio de <xref:System.Windows> nombres. Por este motivo, debe establecer el espacio de nombres en blanco para mantener la calificación de las consultas XPath <xref:System.Windows> por parte del espacio de nombres, lo que dirigirá erróneamente a las consultas.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Como se muestra en este ejemplo, para crear la misma declaración de enlace en la sintaxis de atributo es preciso crear caracteres de escape correctos para los caracteres especiales. Para más información, consulte [XML Character Entities and XAML](../../xaml-services/xml-character-entities-and-xaml.md) (Entidades de caracteres XML y XAML).  
  
 Al ejecutar este ejemplo ,semostraránlossiguienteselementos.<xref:System.Windows.Controls.ListBox> Se trata de los elementos *Title* de todos los elementos que se encuentran bajo *Books* cuyo valor de *Stock* sea "*out*" o cuyo valor de *Number* sea 3 o mayor o igual que 8. Tenga en cuenta que no se devuelve ningún elemento <xref:System.Windows.Data.XmlDataProvider.XPath%2A> de CD porque el <xref:System.Windows.Data.XmlDataProvider> valor establecido en indica que solo se deben exponer los elementos de los *libros* (estableciendo un filtro en esencia).  
  
 ![Captura de pantalla del ejemplo de XPath que muestra el título de cuatro libros.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 En este ejemplo, se muestran <xref:System.Windows.Data.Binding.XPath%2A> los títulos <xref:System.Windows.Controls.TextBlock> de los libros porque el del enlace de <xref:System.Windows.DataTemplate> se establece en "*title*". Si desea mostrar el valor de un atributo, como el *ISBN*, establezca ese <xref:System.Windows.Data.Binding.XPath%2A> valor en "`@ISBN`".  
  
 El método XmlNode.SelectNodes administra las propiedades **XPath** en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Puede modificar las consultas **XPath** para obtener resultados distintos. Estos son algunos ejemplos de la <xref:System.Windows.Data.Binding.XPath%2A> consulta en el enlazado <xref:System.Windows.Controls.ListBox> del ejemplo anterior:  
  
- `XPath="Book[1]"` devolverá el primer elemento de libro ("XML in Action"). Tenga en cuenta que los índices de **XPath** se basan en 1, no en 0.  
  
- `XPath="Book[@*]"` devolverá todos los elementos con cualquier atributo.  
  
- `XPath="Book[last()-1]"` devolverá los elementos de libro del segundo al último ("Introducing Microsoft .NET").  
  
- `XPath="*[position()>3]"` devolverá todos los elementos de libro excepto los 3 primeros.  
  
 Al ejecutar una consulta **XPath** , devuelve un <xref:System.Xml.XmlNode> o una lista de XMLNodes. <xref:System.Xml.XmlNode>es un objeto de Common Language Runtime (CLR), lo que significa que puede <xref:System.Windows.Data.Binding.Path%2A> usar la propiedad para enlazar a las propiedades de Common Language Runtime (CLR). Remítase de nuevo al ejemplo anterior. Si el resto del ejemplo permanece igual y cambia el <xref:System.Windows.Controls.TextBlock> enlace a lo siguiente, verá los nombres de la XMLNodes devuelta en el. <xref:System.Windows.Controls.ListBox> En este caso, el nombre de todos los nodos devueltos es "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 En algunas aplicaciones, puede que no sea conveniente incrustar [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] como una isla de datos dentro del código fuente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ya que es imprescindible conocer el contenido exacto de los datos en tiempo de compilación. Por lo tanto, también se admite la obtención de los datos de un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] externo, como en el ejemplo siguiente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Si los [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos residen en un archivo remoto [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] , debe definir el acceso a los datos mediante la asignación de un apropiado [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] al <xref:System.Windows.Data.XmlDataProvider.Source%2A> atributo como se indica a continuación:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.ObjectDataProvider>
- [Enlazar a los resultados de una consulta LINQ to XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Información general sobre orígenes de enlaces](binding-sources-overview.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
