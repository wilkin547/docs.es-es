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
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174191"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Cómo: Hacer que los datos estén disponibles para el enlace en XAML
En este tema se describen varias formas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]de hacer que los datos estén disponibles para el enlace en , en función de las necesidades de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 Si tiene un objeto de Common Language Runtime (CLR) al que desea enlazar desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], una forma de hacer `x:Key`que el objeto esté disponible para el enlace es definirlo como un recurso y darle un archivo . En el ejemplo siguiente, `Person` tiene un objeto `PersonName`con una propiedad string denominada . El `Person` objeto (en la línea mostrada `<src>` resaltada que contiene `SDKSample`el elemento) se define en el espacio de nombres denominado .  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 A continuación, <xref:System.Windows.Controls.TextBlock> puede enlazar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]control al objeto en `<TextBlock>` , como se muestra la línea resaltada que contiene el elemento.
  
 Como alternativa, puede <xref:System.Windows.Data.ObjectDataProvider> utilizar la clase, como en el ejemplo siguiente:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 El enlace se define de la misma manera, `<TextBlock>` como se muestra la línea resaltada que contiene el elemento.  
  
 En este ejemplo en particular, el resultado <xref:System.Windows.Controls.TextBlock> es el `Joe`mismo: tiene a con el contenido de texto . Sin <xref:System.Windows.Data.ObjectDataProvider> embargo, la clase proporciona funcionalidad como la capacidad de enlazar al resultado de un método. Puede elegir utilizar <xref:System.Windows.Data.ObjectDataProvider> la clase si necesita la funcionalidad que proporciona.  
  
 Sin embargo, si va a enlazar a un objeto `DataContext` que ya se ha creado, debe establecer el código in, como en el ejemplo siguiente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Para obtener acceso a <xref:System.Windows.Data.XmlDataProvider> los datos XML para enlazar mediante la clase, vea [Enlazar a datos XML mediante un XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Para obtener acceso a <xref:System.Windows.Data.ObjectDataProvider> los datos XML para enlazar mediante la clase, vea [Enlazar a XDocument, XElement o LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Para obtener información sobre muchas formas de especificar los datos a los que está enlazando, vea [Especificar el origen](how-to-specify-the-binding-source.md)de enlace . Para obtener información sobre los tipos de datos a los que puede enlazar o cómo implementar sus propios objetos de Common Language Runtime (CLR) para el enlace, vea [Información general sobre orígenes](binding-sources-overview.md)de enlace .  
  
## <a name="see-also"></a>Consulte también

- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas de información](data-binding-how-to-topics.md)
