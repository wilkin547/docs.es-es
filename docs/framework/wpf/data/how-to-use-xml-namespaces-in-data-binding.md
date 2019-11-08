---
title: 'Cómo: Usar espacios de nombres XML en el enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740578"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Cómo: Usar espacios de nombres XML en el enlace de datos
## <a name="example"></a>Ejemplo
 En este ejemplo se muestra cómo controlar los espacios de nombres especificados en el origen de enlace XML.

 Si los datos XML tienen la siguiente definición de espacio de nombres XML:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Puede usar el elemento <xref:System.Windows.Data.XmlNamespaceMapping> para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente. Después, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia al espacio de nombres XML. En el <xref:System.Windows.Controls.ListBox> de este ejemplo se muestra el *título* y el *DC: fecha* de cada *elemento*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> que especifique no tiene que coincidir con el utilizado en el origen XML; Si el prefijo cambia en el origen XML, la asignación sigue funcionando.

 En este ejemplo concreto, los datos XML provienen de un servicio Web, pero el elemento <xref:System.Windows.Data.XmlNamespaceMapping> también funciona con datos XML o XML en línea en un archivo incrustado.

## <a name="see-also"></a>Vea también

- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
