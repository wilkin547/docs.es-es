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
ms.openlocfilehash: 97e878e4932ca9122bf27f76c32d1a56e69f253a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740607"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Cómo: Hacer que los datos estén disponibles para el enlace en XAML
En este tema se describen varias formas de hacer que los datos estén disponibles para el enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], en función de las necesidades de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 Si tiene un objeto Common Language Runtime (CLR) al que le gustaría enlazar desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una manera de hacer que el objeto esté disponible para el enlace es definirlo como un recurso y darle un `x:Key`. En el ejemplo siguiente, tiene un objeto de `Person` con una propiedad de cadena denominada `PersonName`. El objeto `Person` (en la línea que se muestra resaltada que contiene el elemento `<src>`) se define en el espacio de nombres denominado `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Después, puede enlazar el control de <xref:System.Windows.Controls.TextBlock> al objeto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como la línea resaltada que contiene el elemento `<TextBlock>` muestra. 
  
 Como alternativa, puede usar la clase <xref:System.Windows.Data.ObjectDataProvider>, como en el ejemplo siguiente:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 El enlace se define de la misma manera, como se muestra en la línea resaltada que contiene el elemento `<TextBlock>`.  
  
 En este ejemplo concreto, el resultado es el mismo: tiene una <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe`. Sin embargo, la clase <xref:System.Windows.Data.ObjectDataProvider> proporciona funcionalidad como la capacidad de enlazar con el resultado de un método. Puede optar por usar la clase <xref:System.Windows.Data.ObjectDataProvider> si necesita la funcionalidad que proporciona.  
  
 Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer el `DataContext` en el código, como en el ejemplo siguiente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Para obtener acceso a los datos XML para el enlace mediante la clase <xref:System.Windows.Data.XmlDataProvider>, vea [enlazar a datos XML mediante XmlDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Para obtener acceso a los datos XML para el enlace mediante la clase <xref:System.Windows.Data.ObjectDataProvider>, vea [enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Para obtener información acerca de muchas maneras de especificar los datos a los que se enlaza, vea [especificar el origen de enlace](how-to-specify-the-binding-source.md). Para obtener información sobre los tipos de datos a los que puede enlazar o cómo implementar sus propios objetos Common Language Runtime (CLR) para el enlace, consulte [información general sobre orígenes de enlace](binding-sources-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
