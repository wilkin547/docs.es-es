---
title: 'Cómo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath'
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: a5ad7d8bce9bc0a760868e483278d1836f9472af
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559708"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Cómo: Enlazar a datos XML mediante XMLDataProvider y consultas XPath
En este ejemplo se muestra cómo enlazar a datos XML mediante una <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con un <xref:System.Windows.Data.XmlDataProvider>, los datos subyacentes a los que se puede tener acceso a través del enlace de datos en la aplicación pueden ser cualquier árbol de nodos XML. En otras palabras, una <xref:System.Windows.Data.XmlDataProvider> proporciona una manera cómoda de usar cualquier árbol de nodos XML como origen de enlace.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los datos se incrustan directamente como una *isla de datos* XML dentro de la sección <xref:System.Windows.FrameworkElement.Resources%2A>. Una isla de datos XML se debe ajustar en `<x:XData>` etiquetas y siempre tener un solo nodo raíz, que es el *inventario* en este ejemplo.  
  
> [!NOTE]
> El nodo raíz de los datos XML tiene un atributo **xmlns** que establece el espacio de nombres XML en una cadena vacía. Se trata de un requisito para aplicar las consultas XPath a una isla de datos insertada dentro de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En este caso en línea, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]y, por tanto, la isla de datos, hereda el espacio de nombres de <xref:System.Windows>. Por este motivo, debe establecer el espacio de nombres en blanco para mantener las consultas XPath calificadas por el espacio de nombres <xref:System.Windows>, que dirigirá erróneamente a las consultas.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Como se muestra en este ejemplo, para crear la misma declaración de enlace en la sintaxis de atributo es preciso crear caracteres de escape correctos para los caracteres especiales. Para más información, consulte [XML Character Entities and XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md) (Entidades de caracteres XML y XAML).  
  
 El <xref:System.Windows.Controls.ListBox> mostrará los siguientes elementos cuando se ejecute este ejemplo. Se trata de los elementos *Title* de todos los elementos que se encuentran bajo *Books* cuyo valor de *Stock* sea "*out*" o cuyo valor de *Number* sea 3 o mayor o igual que 8. Tenga en cuenta que no se devuelve ningún elemento de *CD* porque el valor de <xref:System.Windows.Data.XmlDataProvider.XPath%2A> establecido en el <xref:System.Windows.Data.XmlDataProvider> indica que solo se deben exponer los elementos de los *libros* (estableciendo un filtro en esencia).  
  
 ![Captura de pantalla del ejemplo de XPath que muestra el título de cuatro libros.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 En este ejemplo, se muestran los títulos de los libros porque el <xref:System.Windows.Data.Binding.XPath%2A> del enlace de <xref:System.Windows.Controls.TextBlock> en el <xref:System.Windows.DataTemplate> se establece en "*title*". Si desea mostrar el valor de un atributo, como el *ISBN*, debe establecer ese <xref:System.Windows.Data.Binding.XPath%2A> valor en "`@ISBN`".  
  
 El método XmlNode.SelectNodes administra las propiedades **XPath** en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Puede modificar las consultas **XPath** para obtener resultados distintos. Estos son algunos ejemplos de la consulta de <xref:System.Windows.Data.Binding.XPath%2A> en la <xref:System.Windows.Controls.ListBox> enlazada del ejemplo anterior:  
  
- `XPath="Book[1]"` devolverá el primer elemento de libro ("XML in Action"). Tenga en cuenta que los índices de **XPath** se basan en 1, no en 0.  
  
- `XPath="Book[@*]"` devolverá todos los elementos con cualquier atributo.  
  
- `XPath="Book[last()-1]"` devolverá los elementos de libro del segundo al último ("Introducing Microsoft .NET").  
  
- `XPath="*[position()>3]"` devolverá todos los elementos de libro excepto los 3 primeros.  
  
 Al ejecutar una consulta **XPath** , devuelve una <xref:System.Xml.XmlNode> o una lista de XMLNodes. <xref:System.Xml.XmlNode> es un objeto Common Language Runtime (CLR), lo que significa que puede usar la propiedad <xref:System.Windows.Data.Binding.Path%2A> para enlazar a las propiedades Common Language Runtime (CLR). Remítase de nuevo al ejemplo anterior. Si el resto del ejemplo permanece igual y cambia la <xref:System.Windows.Controls.TextBlock> enlace a lo siguiente, verá los nombres de la XmlNodes devuelta en el <xref:System.Windows.Controls.ListBox>. En este caso, el nombre de todos los nodos devueltos es "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 En algunas aplicaciones, la incrustación del XML como una isla de datos dentro del origen de la página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede ser inadecuada, ya que el contenido exacto de los datos debe conocerse en tiempo de compilación. Por lo tanto, también se admite la obtención de los datos de un archivo XML externo, como en el ejemplo siguiente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Si los datos XML residen en un archivo XML remoto, debe definir el acceso a los datos asignando una dirección URL adecuada al atributo <xref:System.Windows.Data.XmlDataProvider.Source%2A> como se indica a continuación:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.ObjectDataProvider>
- [Enlazar a los resultados de una consulta LINQ to XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Información general sobre orígenes de enlaces](binding-sources-overview.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
