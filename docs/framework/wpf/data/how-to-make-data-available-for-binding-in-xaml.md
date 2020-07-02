---
title: 'Cómo: Hacer que los datos estén disponibles para el enlace en XAML'
description: Descubra las distintas formas en que puede hacer que los datos estén disponibles según las necesidades de la aplicación en Windows Presentation Foundation (WPF).
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 16618ce8b19f5dd5854c4d126e7fc455f0428a28
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620799"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Cómo: Hacer que los datos estén disponibles para el enlace en XAML
En este tema se describen varias maneras en las que puede hacer que los datos estén disponibles para el enlace en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , en función de las necesidades de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 Si tiene un objeto Common Language Runtime (CLR) con el que le gustaría enlazar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , una manera de hacer que el objeto esté disponible para el enlace es definirlo como un recurso y darle un `x:Key` . En el ejemplo siguiente, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName` . El `Person` objeto (en la línea que se muestra resaltada que contiene el `<src>` elemento) se define en el espacio de nombres denominado `SDKSample` .  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Después, puede enlazar el <xref:System.Windows.Controls.TextBlock> control al objeto de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , como se muestra en la línea resaltada que contiene el `<TextBlock>` elemento.
  
 Como alternativa, puede usar la <xref:System.Windows.Data.ObjectDataProvider> clase, como en el ejemplo siguiente:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 El enlace se define de la misma manera, como se muestra en la línea resaltada que contiene el `<TextBlock>` elemento.  
  
 En este ejemplo concreto, el resultado es el mismo: tiene un <xref:System.Windows.Controls.TextBlock> con el contenido de texto `Joe` . Sin embargo, la <xref:System.Windows.Data.ObjectDataProvider> clase proporciona funcionalidad como la capacidad de enlazar con el resultado de un método. Puede optar por usar la <xref:System.Windows.Data.ObjectDataProvider> clase si necesita la funcionalidad que proporciona.  
  
 Sin embargo, si va a enlazar a un objeto que ya se ha creado, debe establecer `DataContext` en el código, como en el ejemplo siguiente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Para obtener acceso a los datos XML para el enlace mediante la <xref:System.Windows.Data.XmlDataProvider> clase, vea [enlazar a datos XML mediante XmlDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Para obtener acceso a los datos XML para el enlace mediante la <xref:System.Windows.Data.ObjectDataProvider> clase, vea [enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Para obtener información acerca de muchas maneras de especificar los datos a los que se enlaza, vea [especificar el origen de enlace](how-to-specify-the-binding-source.md). Para obtener información sobre los tipos de datos a los que puede enlazar o cómo implementar sus propios objetos Common Language Runtime (CLR) para el enlace, consulte [información general sobre orígenes de enlace](binding-sources-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
