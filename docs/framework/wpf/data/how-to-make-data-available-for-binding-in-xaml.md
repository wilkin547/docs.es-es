---
title: 'Cómo: Hacer que los datos estén disponibles para el enlace en XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 09a6fca48c06efca6f06b9e0617de9095197bd17
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703494"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Cómo: Hacer que los datos estén disponibles para el enlace en XAML
Este tema describen varias maneras de hacer que datos disponibles para enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], según las necesidades de su aplicación.  
  
## <a name="example"></a>Ejemplo  
 Si tiene un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] desea enlazar a partir de objetos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una forma que puede que el objeto esté disponible de enlace consiste en definir como un recurso y asígnele un `x:Key`. En el ejemplo siguiente, tendrá un `Person` objeto con una propiedad de cadena denominada `PersonName`. El `Person` objeto (en la línea que se muestra resaltada que contiene el `<src>` elemento) se define en el espacio de nombres denominado `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 A continuación, puede enlazar el <xref:System.Windows.Controls.TextBlock> control en el objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como el resaltado de línea que contiene el `<TextBlock>` elemento muestra. 
  
 Como alternativa, puede usar el <xref:System.Windows.Data.ObjectDataProvider> (clase), como en el ejemplo siguiente:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Definir el enlace de la misma manera, como la línea resaltada que contiene el `<TextBlock>` muestra de elemento.  
  
 En este ejemplo concreto, el resultado es el mismo: tiene un <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe`. Sin embargo, la <xref:System.Windows.Data.ObjectDataProvider> clase proporciona funcionalidad como la capacidad para enlazar con el resultado de un método. Puede usar el <xref:System.Windows.Data.ObjectDataProvider> si necesita la funcionalidad que proporciona la clase.  
  
 Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer el `DataContext` en código, como en el ejemplo siguiente.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos para el enlace mediante la <xref:System.Windows.Data.XmlDataProvider> de clases, vea [enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Para tener acceso a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos para el enlace mediante la <xref:System.Windows.Data.ObjectDataProvider> de clases, vea [enlazar a XElement, XDocument o LINQ para resultados de consultas XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Para obtener información acerca de muchas maneras puede especificar los datos que se va a enlazar a, vea [especificar el origen de enlace](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Para obtener información sobre qué tipos de datos se puede enlazar o cómo implementar su propio [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objetos para el enlace, consulte [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
