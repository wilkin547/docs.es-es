---
title: 'Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920124"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement

En este ejemplo se muestra cómo enlazar datos XML a un <xref:System.Windows.Controls.ItemsControl> mediante <xref:System.Xml.Linq.XDocument>.

## <a name="example"></a>Ejemplo

El código XAML siguiente define un <xref:System.Windows.Controls.ItemsControl> e incluye una plantilla de datos para los datos de tipo `Planet` en el espacio de nombres `http://planetsNS` XML. Un tipo de datos XML que ocupa un espacio de nombres debe incluir el espacio de nombres entre llaves y, si aparece donde podría aparecer una extensión de marcado XAML, debe preceder al espacio de nombres con una secuencia de escape de llaves. Este código enlaza a las propiedades dinámicas que corresponden a los métodos <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement>. Las propiedades dinámicas permiten a XAML enlazar a las propiedades dinámicas que comparten los nombres de los métodos. Para obtener más información, vea [LINQ to XML propiedades dinámicas](linq-to-xml-dynamic-properties.md). Tenga en cuenta cómo la declaración de espacio de nombres predeterminada para XML no se aplica a los nombres de atributo.

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

En el C# código siguiente se llama a<xref:System.Xml.Linq.XDocument.Load%2A>y se establece el contexto de datos del panel de pila en todos los subelementos del elemento denominado`SolarSystemPlanets`en el espacio de nombres`http://planetsNS`XML.

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

Los datos XML se pueden almacenar como un recurso XAML mediante <xref:System.Windows.Data.ObjectDataProvider>. Para obtener un ejemplo completo, vea el [código fuente L2DBForm. Xaml](l2dbform-xaml-source-code.md). En el ejemplo siguiente se muestra cómo el código puede establecer el contexto de datos en un recurso de objetos.

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

Las propiedades dinámicas que se asignan a <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> proporcionan flexibilidad en XAML. El código también puede enlazar a los resultados de una consulta LINQ to XML. Este ejemplo enlaza a los resultados de la consulta ordenados por un valor de elemento.

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a>Vea también

- [Información general sobre orígenes de enlaces](binding-sources-overview.md)
- [Información general de enlace de datos WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Ejemplo de enlace de datos WPF mediante LINQ to XML](linq-to-xml-data-binding-sample.md)
- [Propiedades dinámicas de LINQ to XML](linq-to-xml-dynamic-properties.md)
